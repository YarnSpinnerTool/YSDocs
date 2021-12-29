# 🤖 Creating Commands and Functions

## Defining Commands

You can define your own commands, which allow the scripts you write in Yarn Spinner to control parts of the game that you've built.

In Unity, there are two ways to add new commands to Yarn Spinner: automatically, via the `YarnCommand` attribute, or manually, using the `DialogueRunner`'s `AddCommandHandler` method.

### The `YarnCommand` attribute

The `YarnCommand` attribute lets you expose methods in a `MonoBehaviour` to Yarn Spinner.

When you add the `YarnCommand` attribute to a method, you specify what name the command should have in Yarn scripts. You can then use that name as a command.

If the method is static, you call it directly. For example:

```csharp
// Note that we aren't subclassing MonoBehaviour here; 
// static commands can be on any class.
public class FadeCamera {

    [YarnCommand("fade_camera")]
    public static void FadeCamera() {
        Debug.Log("Fading the camera!");
    }
}
```

If you save this in a file called `FadeCamera.cs`, you can run this code in your Yarn scripts like this:

```
<<fade_camera>>
// will print "Fading the camera!" in the console
```

If the method is not `static`, you call it with the name of the game object you want the command to run on.

For example:

```csharp
public class CharacterMovement : MonoBehaviour {

    [YarnCommand("jump")]
    public void Jump() {
        Debug.Log($"{name} is jumping!");
    }
}
```

If you save this in a file called `CharacterMovement.cs`, create a new game object called `MyCharacter`, and attach the `CharacterMovement` script to that game object, you can run this code in your Yarn scripts like this:

```
<<jump MyCharacter>>
// will print "MyCharacter is jumping!" in the console
```

You can also use methods that take parameters. Yarn Spinner will take the parameters that you provide, and convert them to the appropriate type.

Methods that are used with `YarnCommand` may take the following kinds of parameters:

| Type                            | Note                                                                                                                                                                                                                                                                                   |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `string`                        | Passed directly to the function.                                                                                                                                                                                                                                                       |
| `int`                           | Parsed as an integer using [Convert.ChangeType](https://docs.microsoft.com/en-us/dotnet/api/system.convert.changetype).                                                                                                                                                                |
| `float`                         | Parsed as an integer using [Convert.ChangeType](https://docs.microsoft.com/en-us/dotnet/api/system.convert.changetype).                                                                                                                                                                |
| `bool`                          | The strings "true" and "false" are converted to their respective boolean values, `true` and `false`. Additionally, the name of the parameter is interpreted as `true`.                                                                                                                 |
| `GameObject`                    | Yarn Spinner will search all active scenes for a game object with the given name. If one is found, that game object will be passed as the parameter; otherwise, `null` will be passed.                                                                                                 |
| `Component` (or its subclasses) | Yarn Spinner will search all active scenes for a game object with the given name, and then attempt to find a component of the parameter's type on that game object or its children. If one is found, that component will be passed as the parameter; otherwise, `null` will be passed. |

Method parameters may be optional.

For example, consider this method:

```csharp
[YarnCommand("walk")]
public void Walk(GameObject destination, bool dancing = false) {
    var position = destination.transform.position;

    // If the second parameter is used in the command,
    // and it's "true" or "dancing", use a dance 
    // animation
    if (dancing) {
        // set animation to a dance
    } else {
        // set animation to a regular walk
    }

    // walk the character to 'position'
}
```

This command could be called like this:

```
<<walk MyCharacter StageLeft>> // walk to the position of the object named 'StageLeft'

<<walk MyOtherCharacter StageRight dancing>> // walk to StageRight, while dancing
```

### Adding commands through code

You can also add new commands directly to a Dialogue Runner, using the `AddCommandHandler` method.

`AddCommandHandler` takes two parameters: the name of the command as it should be used in Yarn Spinner, and a method to call when the function is run.

If you want to add a command using `AddCommandHandler` that takes parameters, you must list the types of those parameters.

For example, to create a command that makes the main camera look at an object, create a new C# script in Unity with the following code:

```csharp
public class CustomCommands : MonoBehaviour {    

    // Drag and drop your Dialogue Runner into this variable.
    public DialogueRunner dialogueRunner;

    public void Awake() {

        // Create a new command called 'camera_look', which looks at a target. 
        // Note how we're listing 'GameObject' as the parameter type.
        dialogueRunner.AddCommandHandler<GameObject>(
            "camera_look",     // the name of the command
            CameraLookAtTarget // the method to run
        );
    }

    // The method that gets called when '<<camera_look>>' is run.
    private void CameraLookAtTarget(GameObject target) {
        if (target == null) {
            debug.Log("Can't find the target!");
        }
        // Make the main camera look at this target
        Camera.main.transform.LookAt(target.transform);
    }    
}
```

Add this script to any game object, and it will register the `camera_look` in the Dialogue Runner you attach.

You can then call this method like this:

```
<<camera_look LeftMarker>> // make the camera look at an object named LeftMarker
```

### Making Commands Using Coroutines

[Coroutines](https://docs.unity3d.com/Manual/Coroutines.html) can be commands. If you register a command, either using the `YarnCommand` attribute, or the `AddCommandHandler` method, and the method you're using it with is a coroutine (that is, it returns `IEnumerator`, and `yields` objects like [`WaitForSeconds`](https://docs.unity3d.com/ScriptReference/WaitForSeconds.html)), Yarn Spinner will pause execution of your dialogue when the command is called.

For example, here's how you'd write your own custom implementation of `<<wait>>`. (You don't have to do this in your own games, because `<<wait>>` is already added for you, but this example shows you how you'd do it yourself.)

```csharp
public class CustomWaitCommand : MonoBehaviour {    

    [YarnCommand("custom_wait"]
    IEnumerator CustomWait() {

        // Wait for 1 second
        yield return new WaitForSeconds(1.0);
        
        // Because this method returns IEnumerator, t's a coroutine. 
        // Yarn Spinner will wait until onComplete is called.
    }    
}
```

This new method, once registered with a Dialogue Runner, can be called like this:

```
<<custom_wait>> // Waits for one second, then continues running
```

## Defining Functions

[Functions](../getting-started/writing-in-yarn/functions.md) are units of code that Yarn scripts can call to receive a value.

In additon to the [built-in functions](../getting-started/writing-in-yarn/functions.md#built-in-functions) that come with Yarn Spinner, you can create your own.

To create a function, you use the `YarnFunction` attribute, or the `AddFunction` method on a Dialogue Runner. These work very similarly to commands, but with two important distinctions:

1. Functions must return a value.
2. Functions are required to be `static`.

For example, here's a custom function that adds two numbers together:

```csharp
public class AdderFunction {
   [YarnFunction("add_numbers")]
   public static int AddNumbers(int first, int second)
   {
       return first + second;
   }
}
```

When this code has been added to your project, you can use it like this:

```
One plus one is {add_numbers(1, 1)}
```

Yarn functions can return the following types of values:

* `string`
* `int`
* `float`
* `bool`

## Commands, Functions and Assembly Definitions

Yarn Spinner searches your code for methods that have the `YarnCommand` and `YarnFunction` attributes when your game first starts up, as well as when a [Dialogue Runner](components/dialogue-runner.md) is told to run a [Yarn Project](importing-yarn-files/yarn-projects.md). 

If the Yarn Project's "Search All Assemblies" option is turned on, every assembly definition is searched; if it's turned off, only the assembly definitions specified in the "Assemblies To Search" option is searched. Code that is not in an assembly definition is always included.

By default, Yarn Spinner searches every assembly definition. If you have a large codebase, putting all of the code that contains commands and functions in an assembly definition can reduce the amount of time Yarn Spinner needs to take to find all of the commands and functions.

{% hint style="info" %}
If "Search All Assemblies" is turned off on your Yarn Projects, and you're seeing errors that mention that a command hasn't been registered, try turning "Search All Assemblies" on. If the error goes away, it means the code for those commands is in an assembly definition that the Yarn Project wasn't using.
{% endhint %}
