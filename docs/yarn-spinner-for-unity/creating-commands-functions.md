---
icon: display-code
---

# Commands and Functions

Custom Commands and Functions are how you are able to let the Yarn Spinner slice of your game integrate closer with the other pieces.
They have a lot of similarities and some differences in how they work, this page will talk mostly about Commands and then in the Functions section describe how they differ.

{% hint style="warning" %}
While the Yarn Spinner side of writing commands and functions is universal there are still quite a few engine specific quirks.
We endeavour to make it so there are as few architectural differences between engines, there will always be changes between tools to better fit the expectations of that engine.
So take everything on this page as how Yarn Spinner for Unity binds your Commands and Functions into your Unity C# code, and not how it works in another engine.
{% endhint %}

### Finding Yarn Commands in your Project

You can see a list of commands that you've registered by opening the Window menu and choosing Yarn Spinner -> Commands.
This will show a list of every command that you can call in your Yarn script as well as what parameters they take.

## Creating Custom Commands

You can define your own commands, which allow the scripts you write in Yarn Spinner to control parts of the game that you've built.

In Unity, there are two ways to add new commands to Yarn Spinner: automatically, via the `YarnCommand` attribute, or manually, using the `DialogueRunner`'s `AddCommandHandler` method.

### The `YarnCommand` attribute

The `YarnCommand` attribute lets you expose methods to Yarn Spinner.

When you add the `YarnCommand` attribute to a method, we use the name of the method as the name of the command.

```csharp
public class GameManager {
    [YarnCommand]
    public static void SaveGame() {
        Debug.Log($"The game is now saved");
    }
}
```

This could then be called from your Yarn Scripts no differently than any other command: `<<SaveGame>>`.

The `YarnCommand` attribute also can have an optional string parameter if you want the command to have a different name from the method name.
The only restriction on this string is it must be known at compile time and must follow the some restrictions for command names in Yarn Spinner, which means: no spaces, no periods, and only basic characters essentially the same rules as what you can name methods in C#.

```csharp
public class GameManager {
    [YarnCommand("save_game")]
    public static void SaveGame() {
        Debug.Log($"The game is now saved");
    }
}
```

Now to call this command you would use the string value provided to the `YarnCommand` attribute: `<<save_game>>`.
In both cases the same method in C# was called, we just changed what name Yarn Spinner understands for that method.

### Parameters in Commands

It is pretty unlikely that all your commands have no parameters, and you can add parameters into your custom commands also.
Yarn will take the parameters you provide and convert them to the appropriate type to provide to the C# method.

```csharp
public class GameManager
{
    static List<string> listOfAllAchievements = new List<string>{"start_game", "pet_the_dog", "finish_game"};
    
    [YarnCommand("unlock_cheevo")]
    public static void UnlockAchievement(string name)
    {
        if (listOfAllAchievements.Contains(name))
        {
            Debug.Log($"Unlocked the {name} achievement!");
            listOfAllAchievements.Remove(name);
        }
        else
        {
            Debug.Log($"Encountered unexpected achievement: {name}");
        }
    }
}
```

Here the `<<unlock_cheevo pet_the_dog>>` command would unlock the achievement, or more specifically it would log out "Unlocked the pet_the_dog achievement!".
The `pet_the_dog` parameter was taken from the command in Yarn and automatically converted into the appropriate type (a string in this case) and provided as the `name` parameter in the `UnlockAchievement` method.

The following types can be used as parameters inside your YarnCommand C# methods:

| Type                            | Note                                                                                                                                                                                                                                       |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `bool`                          | The strings "true" and "false" are converted to their respective boolean values, `true` and `false`. Additionally, the name of the parameter is interpreted as `true`.                                                                     |
| `string`                        | Passed directly to the method as it appears in the command.                                                                                                                                                                                |
| `int`                           | Parsed as an integer using [Convert.ChangeType](https://docs.microsoft.com/en-us/dotnet/api/system.convert.changetype).                                                                                                                    |
| `float`                         | Parsed as a float using [Convert.ChangeType](https://docs.microsoft.com/en-us/dotnet/api/system.convert.changetype).                                                                                                                       |
| `uint`                          | Parsed as an integer using [Convert.ChangeType](https://docs.microsoft.com/en-us/dotnet/api/system.convert.changetype).                                                                                                                    |
| `double`                        | Parsed as a double using [Convert.ChangeType](https://docs.microsoft.com/en-us/dotnet/api/system.convert.changetype).                                                                                                                      |
| `decimal`                       | Parsed as a decimal using [Convert.ChangeType](https://docs.microsoft.com/en-us/dotnet/api/system.convert.changetype).                                                                                                                     |
| `byte`                          | Parsed as a byte using [Convert.ChangeType](https://docs.microsoft.com/en-us/dotnet/api/system.convert.changetype).                                                                                                                        |
| `sbyte`                         | Parsed as a sbyte using [Convert.ChangeType](https://docs.microsoft.com/en-us/dotnet/api/system.convert.changetype).                                                                                                                       |
| `short`                         | Parsed as a short using [Convert.ChangeType](https://docs.microsoft.com/en-us/dotnet/api/system.convert.changetype).                                                                                                                       |
| `ushort`                        | Parsed as a ushort using [Convert.ChangeType](https://docs.microsoft.com/en-us/dotnet/api/system.convert.changetype).                                                                                                                      |
| `long`                          | Parsed as a long using [Convert.ChangeType](https://docs.microsoft.com/en-us/dotnet/api/system.convert.changetype).                                                                                                                        |
| `ulong`                         | Parsed as a ulong using [Convert.ChangeType](https://docs.microsoft.com/en-us/dotnet/api/system.convert.changetype).                                                                                                                       |
| `GameObject`                    | Yarn Spinner will search all active scenes for a game object with the given name. If one is found, that game object will be passed as the parameter.                                                                                       |
| `Component` (or its subclasses) | Yarn Spinner will search all active scenes for a game object with the given name, and then attempt to find a component of the parameter's type on that game object or its children. If one is found, that will be passed as the parameter. |
| Any `YarnConverted` type        | Yarn Spinner will call the appropriate custom converter method for the type using the string value of the parameter in the command. See [Converters](#custom-converters) for details.                                                      |
| Any exported Yarn Enum          | Any Enums in your Yarn that have had their [C# wrapper exported](./components/variable-storage/variable-storage.md#generated-wrapper) see [Enums as Parameters](#enums-as-parameters) for details.                                         |
| `CancellationToken`             | Cancellation tokens work in a very different manner, see [Cancelling Commands](#cancelling-commands) for details on this.                                                                                                                  |
| `LineCancellationToken`         | Line Cancellation tokens work in a very different manner, see [Cancelling Commands](#cancelling-commands) for details on this.                                                                                                             |

#### Optional parameters

Your Commands can have optional parameters.
This is determined by having a default value provided to the parameter in the C# method:

```csharp
public class GameManager
{
    [YarnCommand("save_game")]
    public static void SaveGame(int slot = 0)
    {
        Debug.Log($"The game is now saved into slot: {slot}");
    }
}
```

Then in your Yarn this can be called either with the parameter: `<<save_game 1>>` or without: `<<save_game>>` with the first logging `The game is now saved into slot: 1` and the second `The game is now saved into slot: 0`.
Optional parameters need to go at the end of the Command and cannot be used in conjunction with arrays or cancellation tokens.

#### Parameter arrays

Your Commands can also have parameter arrays, this allows you to provide an arbitrary number of values into the command at once as a single parameter.
The values in the command are parsed and converted individually following the normal conversion rules and then packed into an array and sent over to the C#:

```csharp
public class GameManager
{
    static List<string> listOfAllAchievements = new List<string>{"start_game", "pet_the_dog", "finish_game"};
    
    [YarnCommand("unlock_cheevo")]
    public static void UnlockAchievement(params string[] names)
    {
        foreach (var achievement in names)
        {
            if (listOfAllAchievements.Contains(achievement))
            {
                Debug.Log($"Unlocked the {achievement} achievement!");
                listOfAllAchievements.Remove(achievement);
            }
            else
            {
                Debug.Log($"Encountered unexpected achievement: {achievement}");
            }
        }
    }
}
```

This could then be called in a number of different ways:

```yarn
<<unlock_cheevo>>
<<unlock_cheevo start_game>>
<<unlock_cheevo start_game pet_the_dog>>
```

All of these are a valid way to invoke this command, reflecting zero, one, and two parameters respectively.

Parameter arrays can be used in conjunction with any type and any number of other parameters.
The only restriction is your Command can only have a single parameter array, it must go at the end of the command and cannot be used in conjunction with optional parameters or a cancellation token.

#### Parameter Attributes

There are two parameter attributes you can use on your parameters inside your command methods: `YarnNodeParameterAttribute` and `YarnEnumParameterAttribute`.
These are type hints for the editor and have no impact on parsing or dispatch of commands, but are useful when you want to limit the suggested autocomplete values in the editor while writing your Yarn without changing the value type on the C# side.

The first `YarnNodeParameterAttribute` is only for string parameters in your C# methods and tells the Yarn editor that this parameter should offer suggestions of node names from the project.

```csharp
[YarnCommand("log_important_event")]
public static void Log([YarnNodeParameter] string nodeName)
{
    Debug.Log($"The player has just hit the vital point of the {nodeName} node!");
}
```

`YarnEnumParameterAttribute` is for string parameters in your C# methods and tells the Yarn editor to offer enum cases from the provided type of the enum.

```csharp
[YarnCommand("do_thing")]
public static void DoThing([YarnEnumParameter("MyYarnEnum")] string enum)
{
    Debug.Log($"It's time to do things with the {enum} case from the MyYarnEnum type!");
}
```

{% hint style="warning" %}
These attributes only change the autocomplete behaviour of the editor, they don't change command parsing or invocation.
So this means that you can ignore the suggestions and provide a totally unexpected value and this will be sent along happily by us to your method.
{% endhint %}

### Custom Parameter Types

Most of the parameter types in your Commands will be of a basic type: numbers, booleans, strings or a monobehaviour, so the way to convert between the value in the Yarn command and the parameter in the C# method is obvious for us to handle.
However there are times when you want to use types beyond these and Yarn Spinner for Unity supports two different options here, Enums and YarnConverters.

#### Enums as Parameters

Any [Enums](../write-yarn-scripts/scripting-fundamentals/enums.md) you have defined in your Yarn scripts can be used as a parameter in your Commands.
For us to be able to know what type this should be on the C# side however you have to have [exported the generated Variables file](./components/variable-storage/variable-storage.md#generated-wrapper) which includes the C# equivalent of the Yarn enums as well as the conversion methods we need to convert from the Yarn to the C#.

Meaning if you have the following in your Yarn:

```yarn
<<enum Achievement>>
    <<case StartTheGame>>
    <<case PetTheDog>>
    <<case FinishTheGame>>
<<endenum>>

<<unlock_cheevo Achievement.StartTheGame>>
```

And then if you have exported the generated Variables file then you would be able to bind this to the following C# method:

```csharp
public class GameManager
{
    static List<Achievement> listOfAllAchievements = new List<Achievement>{Achievement.StartTheGame, Achievement.PetTheDog, Achievement.FinishTheGame};
    
    [YarnCommand("unlock_cheevo")]
    public static void UnlockAchievement(Achievement achievement)
    {
        if (listOfAllAchievements.Contains(achievement))
        {
            Debug.Log($"Unlocked the {achievement} achievement!");
            listOfAllAchievements.Remove(achievement);
        }
        else
        {
            Debug.Log($"Encountered unexpected achievement: {achievement}");
        }
    }
}
```

Commands using enums can be called in both their full `<<unlock_cheevo Achievement.StartTheGame>>` and short `<<unlock_cheevo .StartTheGame>>` forms.
Enum parameters can be used in optional parameter and parameter arrays.
Enum parameters can be used regardless of if they are string or numeric backed enums.

#### Custom Converters

Finally you can also use any arbitrary type you want in your Commands as a parameter provided you tell us how to handle the conversion between Yarn and C#.

{% hint style="info" %}
Using custom types is an uncommon use case, but works very well when your game simulation layer isn't built up out of MonoBehaviours and GameObject.
It's very convenient to not have to do all the translation in the Command itself and just be given the final types you need to manipulate.
{% endhint %}

As an example let's say you have a game where the player can find, drop, equip, and dig with a variety of different tools.
Instead of having to work out the context of this inside each command you could write a converter that does all of that up front for you.
The way you can provide a converter is via another attribute on a method, the `YarnConverter` attribute.

```csharp
[YarnConverter(typeof(Tool))]
public static bool TryGetTool(string input, out Tool value)
{
    if (input == "slot1")
    {
        value = GameManager.Player.Inventory[0];
        return true;
    }
    else if (input == "slot2")
    {
        value = GameManager.Player.Inventory[1];
        return true;
    }
    else if (GameManager.Tools.TryGetValue(input, out value))
    {
        return true;
    }
    value = default;
    return true;
}
```

So now we've got a method that understands it could be directly manipulating one of the current items the player is using, or it could be any named tool in the game.
To make use of this though `YarnConverter` methods have some very specific requirements.

First they must be `public`, `static`, and return a `bool`.
The boolean return should indicate the success or failure of the conversion, true if the conversion worked, false if it failed.
The method needs to take two parameters, a `string` and and an `out` parameter of the converted type.
The string parameter will be the value from the Yarn command and in our example converter above will be provided as the `input` parameter.
The out parameter of the converter method will need to on a type that is also `public`, and the `Type` of that type (thanks C#) will need to be provided as a value inside the `YarnConverter` attribute itself.
The name of the method and parameters can be anything that you want however.

Once that is all done though you can just use the type as you would any other parameter type in your Commands:

```csharp
[YarnCommand]
public static void Dig(Tool tool)
{
    Debug.Log($"I am digging a hole with {tool}");
    tool.durability--;
}
```

```yarn
Player: I guess I need to pick what to do here

-> Dig a hole
    <<dig slot1>>
-> Use that pitchfork over there
    <<dig pitchfork>>
-> Give up
    Player: yeah why even bother
```

`YarnConverter` types can be used in parameter arrays, and alongside any other parameter types including other `YarnConverter` types.

{% hint style="info" %}
The name of the converter method doesn't matter but we recommend calling it something like `TryGetType` or `TryConvertType`.
{% endhint %}

### Async Commands

So far all the methods we've been talking about have synchronous methods, that is to say they return `void`.
Yarn Spinner will consider these commands to finish instantly and will run through them in the same frame that they are dispatched.
From a practical perspective this means the commands shouldn't take any time to finish, and if they do spin off any long running tasks Yarn Spinner won't wait for them.
If you want to take time you should make the command asynchronous.

{% hint style="info" %}
We have a [page](./components/asynchronous-programming.md) on what async programming means in Yarn Spinner for Unity and we suggest reading that if you are after more detail on how async works.
{% endhint %}

Yarn Spinner for Unity will consider any command which returns a supported awaiter as being an async command and will await that command finishing before continuing.
Async Commands will otherwise work identically to other commands and follow all the same rules and features.

```csharp
[YarnCommand("move_cube")]
public async static YarnTask MoveCube(float duration)
{
    var cube = GameObject.Find("Cube");
    if (cube == null)
    {
        Debug.LogError("Unable to move the cube because we can't find it!");
        return;
    }

    var end = new Vector3(-5, 5, 0);
    float accumulator = 0f;
    while (accumulator < duration)
    {
        cube.transform.position = Vector3.Lerp(Vector3.zero, end, accumulator / duration);
        accumulator += Time.deltaTime;
        await YarnTask.Yield();
    }
    cube.transform.position = end;
}
```

Here we have a very basic command which will move a cube in the scene from the origin to near the top left of the screen and it waits for a frame at each step.

```yarn
Beginning the cube move!
<<move_cube 3>>
Cube movement complete
```

From the Yarn side of things it was just another command, nothing special, but in Unity the game waits for the command to finish before advancing onwards to the line.
So you would see "Beginning the cube move!" appear, then over three seconds the cube would do it's crawl upwards, and then "Cube movement complete".

{% hint style="warning" %}
You can also make durative commands (so ones that don't instantly finish) using coroutines to mimic the behaviour of being async, but this is generally not recommended vs making them "proper" async commands.
Any Command which returns an `IEnumerator` or `Coroutine` instead of `void` will be treated as if they were an async command and we will wait for them to finish before advancing the same as async commands.
The main difference is these cannot be cancelled or hurried-up, making them stricly less flexible than their full async command bretheren.
{% endhint %}

#### Cancelling Commands

One of the main reasons to make your Commands async is so that you can hurry up and cancel them in the same manner as you would lines of dialogue.
To make a command cancellable or hurry-up-able you will need to add a new parameter to the command.
It can be named anything you want but must be either a `CancellationToken` or `LineCancellationToken` and it must be the last parameter in the method.

```csharp
[YarnCommand("move_cube")]
public async static YarnTask MoveCube(float duration, CancellationToken token)
{
    var cube = GameObject.Find("Cube");
    if (cube == null)
    {
        Debug.LogError("Unable to move the cube because we can't find it!");
        return;
    }

    var end = new Vector3(-5, 5, 0);
    float accumulator = 0f;
    while (accumulator < duration && !token.IsCancellationRequested)
    {
        cube.transform.position = Vector3.Lerp(Vector3.zero, end, accumulator / duration);
        accumulator += Time.deltaTime;
        await YarnTask.Yield();
    }
    cube.transform.position = end;
}
```

This code is almost identical to what we had before, but now we have the cancellation token parameter and we are checking if it has been cancelled before we lerp the cube.
Meaning at each step we check if the user has requested to move along to the next piece of dialogue or not.

Unlike the other parameters encountered so far the cancellation tokens works quite a bit differently, it's not a parameter you (as the writer) needs to provide in your Yarn files.
We will create and provide a valid cancellation token (of either type) for your methods to introspect.
Essentially the parameter only exists for C# to make use of, Yarn Spinner doesn't know about it.
So to call this command, nothing has changed in the yarn from when we saw it above, the difference is now we can skip this command and have the cube end up in it's right spot:

```yarn
Beginning the cube move!
<<move_cube 3>>
Cube movement complete
```

Your commands can be hurried-up or cancelled by calling the `HurryUpContent` and `RequestNextContent` methods on the dialogue runner, the same methods for hurrying-up and advancing lines.
If you provide a `CancellationToken` it will be bound to the current contents hurry up source, essentially meaning regardless of if the user requests a hurry up or an advance you will get the same "I have been cancelled" state change.
If you provide a `LineCancellationToken` it is still bound to the current contents source but you can tell the difference between advancing and hurrying-up.

As to what hurrying-up vs cancelling a command means depends entirely on your game and your commands.
The tokens provided let you know that the user has requested a hurry-up or advancement of content, not how that should be handled.
In our example here we are just using the token to tell the cube to get right to the end, the cube will just instantly teleport to the final position if cancelled.

### Instance vs Static

All the commands shown so far have been static commands, methods which have been declared as static and the commands aren't called on any specific target inside the game.
There are plenty of times where you want instead your commands to only target a specific piece of the game, often important characters and other NPCs.
In these case you want it to be an instance command.

To declare a command as an instance command do not add the `static` keyword to the method.

```csharp
public class NPC : MonoBehaviour
{
    [YarnCommand("look")]
    public void LookAt(GameObject lookTarget)
    {
        if (lookTarget == null)
        {
            Debug.LogError($"{this.name} is unable to look at the target, it is null");
        }
        this.transform.LookAt(lookTarget.transform.position);
    }
}
```

There are a few implications for instance commands though, first the type containing the method must either be a `Component` (or `Component` subclass such as `MonoBehaviour`) or must be a type that has a `YarnConverter` method for it.
Here we have defined a new instance command on the `NPC` class, meaning any `NPC` in the scene can perform the `look` command and they will rotate to face some other object in the scene.
In our case the type is `NPC` and it's a public `MonoBehaviour` so we are fine.

The second implication is now in your Yarn you will need to provide a new parameter, the target.
This is always the first parameter, is always a string, and is *either* the value provided as input to the appropriate `YarnConverter` method, or is the name of a game object in the scene that contains the target component and will be found using a `GameObject.Find()` call.
This parameter only exists on the Yarn side of things, in C# it just becomes the instance object (so the `this` of the current instance) the method is called upon:

```yarn
Player: what's that over there?
<<look Alice Desk>>
Alice: hmm, a note?
```

So in our example here the `NPC` in the scene named `Alice` will be the instance, and a game object called `Desk` in the scene will be the `lookTarget` of the `LookAt` method.
Alice was found by doing a `GameObject.Find("Alice")` and then a `GetComponentInChildren<NPC>()` call on that game object.

### Public vs Private

Similarly all command examples shown so far have been public methods, and this is the recommended way of declaring your commands.
You can use private methods, however there is a catch so we don't generally suggest doing this.
The reason we recommend this is twofold, first of all it makes a lot of sense from a design perspective, Yarn is an external part of your game from the objects it can send messages to and you wouldn't normally expect to call private methods on objects.
Secondly by making your methods private we have to use reflection to find and invoke them.
When you methods are public we can directly call them without any form of indirection, literally just call the method as is.
Doing it via reflection is slower, is more error prone, and harder to debug on both your end and ours.

Otherwise private commands work in an identical fashion to public methods and all features of commands and parameters behave the same way.

### Adding commands through code

You can also add new commands directly to a Dialogue Runner, using the `AddCommandHandler` method.

`AddCommandHandler` takes two parameters: the name of the command as it should be used in Yarn Spinner, and a method to call when the function is run.

If you want to add a command using `AddCommandHandler` that takes parameters, you must list the types of those parameters.

For example, to create a command that makes the main camera look at an object:

```csharp
public class CustomCommands : MonoBehaviour
{    
    public DialogueRunner dialogueRunner;

    public void Awake()
    {
        dialogueRunner.AddCommandHandler<GameObject>(
            "camera_look",     // the name of the command
            CameraLookAtTarget // the method to run
        );
    }

    public static void CameraLookAtTarget(GameObject target)
    {
        if (target == null)
        {
            debug.Log("Can't find the target!");
        }
        Camera.main.transform.LookAt(target.transform);
    }
}
```

Add this script to any game object, and it will register the `camera_look` in the Dialogue Runner you attach.

You can then call this method like this:

```
<<camera_look LeftMarker>>
```

### YarnCommand vs AddCommandHandler

We provide two different means of handling commands in Yarn Spinner: the `AddCommandHandler` method and the `YarnCommand` attribute.
Both of these provide effectively the same functionality, and under-the-hood the `YarnCommand` attribute is basically a wrapper around the `AddCommandHandler` call.
So if there are two different ways to achieve the same thing when should you use each one?

* The `YarnCommand` attribute allows you to tag specific methods as being a command, Yarn Spinner will then automatically handle the binding and connection of the the command in Yarn to the method call in C#.
* `AddCommandHandler` method allows you to manually connect a method in C# to a command in Yarn, letting you set the name of the command and which method it connect to.

Most of the time, we feel that the `YarnCommand` attribute should be your default option, because it is easier to use, and maps well to how we find most people use commands - that is calling methods already written for other purposes on your GameObjects.
This does however mean there is now not a clear entry-point for understanding where and what is a command, your commands are essentially strewn all over the place, at the whim of how you laid out your C# code.

The `YarnCommand` attribute works best in our opinion when your commands are calling into specific GameObjects in your scene, which means that it works very well for moving, animating, or changing characters and items in a scene in some way.
When using the the attribute you are essentially adding an additional feature to your method, being able for it to be called via Yarn.
For larger gameplay changing moments, such as loading new scenes, moving between dialogue and the rest of your game, or for more global events like saving the game or unlocking an achievement, the `AddCommandHandler` method is probably more aligned with what you want.
Because these pieces tend to all be in one place it is convenient to be able to see all the functionality at once as a series of `AddCommandHandler` calls.

Regardless of your choice there is no significant difference and is mostly a personal preference.
And our preference is it's probably easier to start with the attribute and change if you don't like it.

{% hint style="info" %}
Because we use Source Generators as part of our command dispatch system there is *technically* a performance improvement in scanning your source code for commands when using the attribute over using direct registration.
Unless you have an enormously large number of commands however this is unlikely to be much of a difference.
{% endhint %}

## Defining Functions

Functions work in a very similar fashion to Commands, with similar rules and restrictions.
For the most part you can assume everything said above for Commands also applies to Functions with the following differences.

### Registrations

Functions are registered via an attribute or directly via code the same as commands, but the attribute is now the `YarnFunction` attribute, and the `AddFunction` method on the Dialogue Runner.
Everything that was said about the command equivalents, and the same advice for their relative strengths and weaknesses are the same.

### Value Return

Because Functions are intended to be the mechanism by which you can provide values directly to Yarn, as such your methods in C# registered as functions **must** return a value, they cannot return `void`.
Yarn functions can return the following types of values and must return a value that is of one of these types:

* `string`
* `int`
* `float`
* `bool`
* `uint`
* `double`
* `decimal`
* `byte`
* `sbyte`
* `short`
* `ushort`
* `long`
* `ulong`

```csharp
[YarnFunction("evil_d6")]
public static int EvilDice()
{
    var roll = UnityEngine.Random.Range(1,7);
    if (roll == 6)
    {
        Debug.Log("tee hee hee, I am the evil dice!");
        roll = 5;
    }
    return roll;
}
```

Here is a example of a valid function, it returns an int between 1-6 which it then reduces it to 5 if it was 6, because the dice is evil.

### Async Functions

Similar again to commands you can make async functions by having them return an awaitable type.
Unlike commands you must use the generic form of those types so you can return a value as well.
The allowed generic types are the same as the return types of a non-async function.

```csharp
[YarnFunction("evil_d6")]
public async static YarnTask<int> EvilDice()
{
    // we get our roll
    var roll = UnityEngine.Random.Range(1,7);

    // we make the dice appear
    await AnimateDiceIntoExistence();
    // we animate it to our roll
    await AnimateDiceToFace(roll);

    // because the dice is evil if it was a 6 we animate it back down to 5
    if (roll == 6)
    {
        await AnimateDiceToFace(5);
        await LaughSound();
        roll = 5;
    }

    // we hide our dice
    await AnimateDiceOutOfExistence();

    // now we return our roll
    return roll;
}
```

This is an example of a valid async function, we've adapted our previous `evil_d6` function into an async form.
It still returns an int but does so through the result of a `YarnTask<>` and has some little animations and audio (assuming we actually wrote those additional methods...) to help juice the effect of the evilness of the dice.

Async functions can also take cancellation tokens as a parameter to let you skip them, however because of how we call functions the concept of hurrying up doesn't really make sense.
This means the Line Cancellation type isn't allowed as a parameter but the Cancellation Token type is:

```csharp
[YarnFunction("evil_d6")]
public async static YarnTask<int> EvilDice(CancellationToken token)
{
    // we get our roll
    var roll = UnityEngine.Random.Range(1,7);

    // we make the dice appear
    await AnimateDiceIntoExistence(token);
    // we animate it to our roll
    await AnimateDiceToFace(roll, token);

    // because the dice is evil if it was a 6 we animate it back down to 5
    if (roll == 6)
    {
        await AnimateDiceToFace(5, token);
        await LaughSound(token);
        roll = 5;
    }

    // we hide our dice
    await AnimateDiceOutOfExistence(token);

    // now we return our roll
    return roll;
}
```

Unlike commands you can't make an async function from a coroutine as there is no way to return a value from a coroutine.
