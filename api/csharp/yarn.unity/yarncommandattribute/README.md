# YarnCommandAttribute

An attribute that marks a method on a  as a \[command\]\( \).

```csharp
public class YarnCommandAttribute : System.Attribute
```

## Remarks

When a [`DialogueRunner`](../dialoguerunner/) receives a , and no command handler has been installed for the command, it splits it by spaces, and then checks to see if the second word, if any, is the name of any s in the scene.

If one is found, it is checked to see if any of the

s attached to the class has a [`YarnCommandAttribute`](./) whose [`CommandString`](yarncommandattribute.commandstring.md) matching the first word of the command.

If a method is found, its parameters are checked:

* If the method takes a single \[\] parameter, the method is called, and will be passed an array containing all words in the command after the first two.
* If the method takes a number of  parameters equal to the number of words in the command after the first two, it will be called with those words as parameters.
* Otherwise, it will not be called, and a warning will be issued.

### `YarnCommand`s and Coroutines

This attribute may be attached to a coroutine.

 The [`DialogueRunner`](../dialoguerunner/) determines if the method is a coroutine if the method returns . 

If the method is a coroutine, the DialogueRunner will pause execution until the coroutine ends.

## Example

The following C\# code uses the `YarnCommand` attribute to register commands.

```csharp
class ExampleBehaviour : MonoBehaviour {
   [YarnCommand("jump")] 
   void Jump()
   {
       Debug.Log($"{this.gameObject.name} is jumping!");
   }

   [YarnCommand("walk")] 
   void WalkToDestination(string destination) {
       Debug.Log($"{this.gameObject.name} is walking to {destination}!");
   }

   [YarnCommand("shine_flashlight")] 
   IEnumerator ShineFlashlight(string durationString) {
       float.TryParse(durationString, out var duration);
       Debug.Log($"{this.gameObject.name} is turning on the flashlight for {duration} seconds!");
       yield new WaitForSeconds(duration);
       Debug.Log($"{this.gameObject.name} is turning off the flashlight!");
   }
}
```

Next, assume that this `ExampleBehaviour` script has been attached to a  present in the scene named "Mae". The `Jump` and `WalkToDestination` methods may then be called from a Yarn script like so:

```text
// Call the Jump() method in the ExampleBehaviour on Mae
<<jump Mae>>

// Call the WalkToDestination() method in the ExampleBehaviour 
// on Mae, passing "targetPoint" as a parameter
<<walk Mae targetPoint>>

// Call the ShineFlashlight method, passing "0.5" as a parameter;
// dialogue will wait until the coroutine ends.
<<shine_flashlight Mae 0.5>>
```

Running this Yarn code will result in the following text being logged to the Console:

```text
Mae is jumping! 
Mae is walking to targetPoint! 
Mae is turning on the flashlight for 0.5 seconds!
(... 0.5 seconds elapse ...)
Mae is turning off the flashlight!
```

## Properties

| Name | Description |
| :--- | :--- |
| [`CommandString`](yarncommandattribute.commandstring.md) | The name of the command, as it exists in Yarn. |

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/DialogueRunner.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/DialogueRunner.cs#L1405), line 1405.

