# Defining Commands and Functions

## Defining Commands

You can define your own commands, which allow the scripts you write in Yarn Spinner to control parts of the game that you've built.

In Unity, there are two ways to add new commands to Yarn Spinner: automatically, via the `YarnCommand` attribute, or manually, using the `DialogueRunner`'s `AddCommandHandler` method.

### The `YarnCommand` attribute

The `YarnCommand` attribute lets you expose methods in a `MonoBehaviour` to Yarn Spinner. 

When you add the `YarnCommand` attribute to a method, you specify what name the command should have in Yarn scripts. You can then use that name, along with the name of the game object that should receive that command, as a command.

For example:

```csharp
public class CharacterMovement : MonoBehaviour {

    [YarnCommand("jump")]
    public void Jump() {
        Debug.Log("Jumping!");
    }
}
```

If you save this in a file called `CharacterMovement.cs`, create a new game object called `MyCharacter`, and attach the `CharacterMovement` script to that game object, you can run this code in your Yarn scripts like this:

```yarn
<<jump MyCharacter>>
// will print "Jumping!" in the console
```

You can also use methods that take parameters. All parameters must be `string`s, and when you call the command, you must provide the same number of parameters as the method expects.

For example, consider this method:

```csharp

[YarnCommand("walk")]
public void Walk(string destinationName) {
    // figure out the position of the object 
    // 'destinationName' and start walking to it
}
```

This command could be called like this:

```yarn
<<walk MyCharacter StageLeft>> // walk to the position of the object named 'StageLeft'
```


### Adding commands through code

You can also add new commands directly to a Dialogue Runner, using the `AddCommandHandler` method.

There are two versions of the `AddCommandHandler` method: one for *non-blocking* commands, and one for *blocking* commands. When your Yarn script calls a blocking command, the dialogue waits until the work is done. Non-blocking commands don't make your Yarn script wait - after the command is called, the script moves on to the next line right away.

Both versions of `AddCommandHandler` take two parameters: the name of the command, and a [delegate](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/delegates/) (that is, a reference to a method, or an in-line function) to run when the command is called. A command will either be blocking or non-blocking depending on the method signature of the delegate.

#### Non-blocking commands

To create a new non-blocking command, create a method that returns `void`, and takes a single parameter: an array of `string`s. This array will contain all of the parameters that were included after the name of the command. It's up to your function to convert these strings to other types, like numbers or references to game objects.

Once this method returns, the Dialogue Runner will continue executing code.

For example, to create a non-blocking command that makes the main camera look at an object, create a new C# script in Unity with the following code:

```csharp
public class CustomCommands : MonoBehaviour {    

    // Drag and drop your Dialogue Runner into this variable.
    public DialogueRunner dialogueRunner;

    public void Awake() {

        // Create a new command called 'camera_look', which looks at a target.
        dialogueRunner.AddCommandHandler(
            "camera_look",     // the name of the command
            CameraLookAtTarget // the method to run
        );
    }

    // The method that gets called when '<<camera_look>>' is run.
    private void CameraLookAtTarget(string[] parameters) {

        // Take the first parameter, and use it to find the object
        string targetName = parameters[0];
        GameObject target = GameObject.Find(targetName);

        // Log an error if we can't find it
        if (target == null) {
            Debug.LogError($"Cannot make camera look at {targetName}:" + 
                "cannot find target");
            return;
        }

        // Make the main camera look at this target
        Camera.main.transform.LookAt(target.transform);
    }    
}
```

Add this script to any game object, and it will register the `camera_look` in the Dialogue Runner you attach.

You can then call this method like this:

```yarn
<<camera_look LeftMarker>> // make the camera look at an object named LeftMarker
```

#### Blocking Commands

Blocking commands are commands that make Yarn Spinner wait. Execution of your Yarn script won't continue until the command indicates that it's done.

To create a new blocking command, create a new method that takes *two* parameters: an array of `string`s, and a `System.Action`. The array of strings is the list of parameters that were passed to the command, and the `Action` is a delegate that your method calls when the work is done. Yarn Spinner won't run any more code until you call the `Action`.

For example, here's how you'd write your own custom implementation of `<<wait>>`. (You don't have to do this in your own games, because `<<wait>>` is already added for you, but this example shows you how you'd do it yourself.)

```csharp
public class CustomWaitCommand : MonoBehaviour {    

    // Drag and drop your Dialogue Runner into this variable.
    public DialogueRunner dialogueRunner;

    public void Awake() {

        // Create a new command called 'custom_wait', which waits for one second.
        dialogueRunner.AddCommandHandler(
            "custom_wait",
            CustomWait
        );
    }

    // The method that gets called when '<<custom_wait>>' is run.
    private void CustomWait(string[] parameters, System.Action onComplete) {

        // Start a coroutine that waits for one second:
        StartCoroutine(DoWait(onComplete));

        // Because this method takes a System.Action parameter, it's a blocking
        // command. Yarn Spinner will wait until onComplete is called.
    }    

    private IEnumerator DoWait(System.Action onComplete) {

        // Wait for 1 second
        yield return new WaitForSeconds(1.0);

        // Call the completion handler
        onComplete();

        // Yarn Spinner will now continue running!
    }
}
```

This new method, once registered with a Dialogue Runner, can be called like this:

```yarn
<<custom_wait>> // Waits for one second, then continues running
```

Note that if you define a custom command that takes a completion handler, you must call the completion handler after the work is done. If you don't, Yarn Spinner will never continue running.
