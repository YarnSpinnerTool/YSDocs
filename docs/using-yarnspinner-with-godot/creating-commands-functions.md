# 🤖 Commands and Functions

## Defining Commands

You can define your own commands, which allow the scripts you write in Yarn Spinner to control parts of the game that you've built.

In Godot, there are two ways to add new commands to Yarn Spinner: automatically, via the `YarnCommand` attribute, or manually, using the `DialogueRunner`'s `AddCommandHandler` method.

If you are using the [Yarn Spinner Extension for Visual Studio Code](../getting-started/editing-with-vs-code/installing-the-extension.md), commands added with the `YarnCommand` attribute will automatically be found by the extension. For commands and functions that you add via `AddCommandHandler` or `AddFunction`, see [here](https://github.com/YarnSpinnerTool/VSCodeExtension?tab=readme-ov-file#defining-custom-commands-for-non-unity-games) for information about exposing your commands and functions to the extension. 

### The `YarnCommand` attribute

The `YarnCommand` attribute lets you expose methods on a `Node` to Yarn Spinner.

When you add the `YarnCommand` attribute to a method, you specify what name the command should have in Yarn scripts. You can then use that name as a command.

If the method is not `static`, you call it with the name of the node you want the command to run on.

For example, if you have a script called `CharacterMovement` that has a method `Leap`, you can add a `YarnCommand` attribute to it to make it available to your Yarn scripts:

```csharp
using Godot;
using YarnSpinnerGodot;
public partial class CharacterMovement : Node {

    [YarnCommand("leap")]
    public void Leap() {
        GD.Print($"{name} is leaping!");
    }
}
```

If you save this in a file called `CharacterMovement.cs`, create a new node called `MyCharacter`, and add the `CharacterMovement` script on that node, you can run this code in your Yarn scripts like this:

```
<<leap MyCharacter>>
// will print "MyCharacter is leaping!" in the console
```

If the method is static, you call it directly, without providing a node name. For example:

```csharp
using Godot;
using YarnSpinnerGodot;
// Note that we aren't subclassing Node here; 
// static commands can be on any class.
public class FadeCamera {

    [YarnCommand("fade_camera")]
    public static void FadeCamera() {
       GD.Print("Fading the camera!");
    }
}
```

If you save this in a file called `FadeCamera.cs`, you can run this code in your Yarn scripts like this:

```
<<fade_camera>>
// will print "Fading the camera!" in the console
```

You can also use methods that take parameters. Yarn Spinner will take the parameters that you provide, and convert them to the appropriate type.

Methods that are used with `YarnCommand` may take the following kinds of parameters:

| Type                            | Note                                                                                                                                                                                                                                                                                   |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `string`                        | Passed directly to the function.                                                                                                                                                                                                                                                       |
| `int`                           | Parsed as an integer using [Convert.ChangeType](https://docs.microsoft.com/en-us/dotnet/api/system.convert.changetype).                                                                                                                                                                |
| `float`                         | Parsed as an integer using [Convert.ChangeType](https://docs.microsoft.com/en-us/dotnet/api/system.convert.changetype).                                                                                                                                                                |
| `bool`                          | The strings "true" and "false" are converted to their respective boolean values, `true` and `false`. Additionally, the name of the parameter is interpreted as `true`.                                                                                                                 |
| `Node`                    | Yarn Spinner will search the scene tree for a node with the given name. If one is found, that node will be passed as the parameter; otherwise, `null` will be passed.                                                                                                 |


### Adding commands through code

You can also add new commands directly to a Dialogue Runner, using the `AddCommandHandler` method.

`AddCommandHandler` takes two parameters: the name of the command as it should be used in Yarn Spinner, and a method to call when the function is run.

If you want to add a command using `AddCommandHandler` that takes parameters, you must list the types of those parameters.

For example, to create a command that makes the main camera look at an object, create a new C# script in Godot with the following code:

```csharp
using Godot;
using YarnSpinnerGodot;

public partial class CustomCommands : Node{    

    // Drag and drop your Dialogue Runner into this variable.
    [Export] public DialogueRunner dialogueRunner;

    public override void _Ready() {

        // Create a new command called 'camera_look', which frees a node from the scene,
        // causing it to be deleted.
        // Note how we're listing 'Node' as the parameter type.
        dialogueRunner.AddCommandHandler<Node>(
            "free_node",     // the name of the command
            FreeNode // the method to run
        );
    }

    // The method that gets called when '<<free_node>>' is run.
    private void FreeNode(Node target) {
        if (!IsInstanceValid(target)) {
            GD.Print("Can't find the target!");
            return;
        }
        // free the target
        target.QueueFree();
    }    
}
```

Add this script to any node, and it will register the `free_node` in the Dialogue Runner you attach.

You can then call this method like this:

```
<<free_node Enemy1>> // frees the node called Enemy1
```

### YarnCommand vs AddCommandHandler

We provide two different means of handling commands in Yarn Spinner: the `AddCommandHandler` method and the `YarnCommand` attribute. Both of these provide effectively the same functionality, and under-the-hood the `YarnCommand` attribute is even a wrapper around the `AddCommandHandler` call. So if there are two different ways to achieve the same thing when should you use each one?

* The `YarnCommand` attribute allows you to tag specific methods as being a command, Yarn Spinner will then automatically handle the binding and connection of the command in text to the method call in C#.
* `AddCommandHandler` method allows you to manually connect a method in C# to a command in Yarn, letting you set the name of the command and which method it connects to, giving you the control over the binding.

Most of the time, we feel that the `YarnCommand` attribute is the better option, because it is easier to use, and maps well to how we find most people use commands - that is, calling specific methods on specific Nodes.

This convenience, however, does come at a cost of flexibility, because your `YarnCommands` either need to be on static methods, or follow specific calling conventions, which may not be what you need or want.

The `YarnCommand` attribute works best in our opinion when your commands are calling into specific Nodes in your scene, which means that it works very well for moving, animating, or changing characters and items in a scene.

For larger gameplay changing moments, such as loading new scenes, moving between dialogue and the rest of your game, or for more global events like saving the game or unlocking an achievement, the `AddCommandHandler` method is better.

### Making Commands Using Async Tasks

[Async tasks](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/) can be commands. If you register a command, either using the `YarnCommand` attribute, or the `AddCommandHandler` method, and the method you're using it with returns a Task, Yarn Spinner will pause execution of your dialogue when the command is called.

For example, here's how you'd write your own custom implementation of `<<wait>>`. (You don't have to do this in your own games, because `<<wait>>` is already added for you, but this example shows you how you'd do it yourself.)

```csharp
public partial class CustomWaitCommand : Node{    

    [YarnCommand("custom_wait")]
    static async Task CustomWait() {

        // Wait for 1 second
        var mainLoop = Engine.GetMainLoop();
        var sceneTree = mainLoop as SceneTree;
        var timer = sceneTree.CreateTimer(1.0);
        await mainLoop.ToSignal(timer, SceneTreeTimer.SignalName.Timeout);
        
        // Because this method returns Task, it's an async command.
        // Yarn Spinner will wait until this method returns.
    }    
}
```

This new method can be called like this:

```
<<custom_wait>> // Waits for one second, then continues running
```

## Defining Functions

[Functions](../getting-started/writing-in-yarn/functions.md) are units of code that Yarn scripts can call to receive a value.

In addition to the [built-in functions](../getting-started/writing-in-yarn/functions.md#built-in-functions) that come with Yarn Spinner, you can create your own.

To create a function, you use the `YarnFunction` attribute, or the `AddFunction` method on a Dialogue Runner. These work very similarly to commands, but with two important distinctions:

1. Functions must return a value.
2. Functions registered via the `YarnFunction` attribute are required to be `static`.

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

When this code has been added to your project, you can use it in any expression, like an `if` statement, or inside a line:

```
<<if add_numbers(1,1) == 2>>
   One plus one is {add_numbers(1, 1)}
<<endif>>
```

Yarn functions can return the following types of values:

* `string`
* `int`
* `float`
* `bool`

