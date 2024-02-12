# DialogueViewBase

Class in [Yarn.Unity](../)

Inherits from `UnityEngine.MonoBehaviour`

## Summary

A `UnityEngine.MonoBehaviour` that can present lines and options to the user, when it receives them from a [DialogueRunner](../yarn.unity.dialoguerunner/) .

```csharp
public abstract class DialogueViewBase : MonoBehaviour
```

## Remarks

When the Dialogue Runner encounters content that the user should see - that is, lines or options - it sends that content to all of the dialogue views stored in [dialogueViews](../yarn.unity.dialoguerunner/yarn.unity.dialoguerunner.dialogueviews.md). The Dialogue Runner then waits until all Dialogue Views have reported that they have finished presenting the content.

To use this class, subclass it, and override its methods. Some of the more common methods you may wish to override are: [RunLine(LocalizedLine,Action)](yarn.unity.dialogueviewbase.runline.md), [InterruptLine(LocalizedLine,Action)](yarn.unity.dialogueviewbase.interruptline.md), [DismissLine(Action)](yarn.unity.dialogueviewbase.dismissline.md) and [RunOptions(DialogueOption\[\],Action\<int>)](yarn.unity.dialogueviewbase.runoptions.md).

Once you have written your subclass, attach it as a component to a `UnityEngine.GameObject`, and add this game object to the list of Dialogue Views in your scene's [DialogueRunner](../yarn.unity.dialoguerunner/).

Dialogue Views do not need to handle every kind of content that the Dialogue Runner might produce. For example, you might have one Dialogue View that handles Lines, and another that handles Options. The built-in [LineView](../yarn.unity.lineview/) class is an example of this, in that it only handles Lines and does nothing when it receives Options.

You may also have multiple Dialogue Views that handle the _same_ kind of content. For example, you may have a Dialogue View that receives Lines and uses them to play voice-over audio, and a second Dialogue View that also receives Lines and uses them to display on-screen subtitles.

## Fields

| Name                                                                | Description                                                                                  |
| ------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| [requestInterrupt](yarn.unity.dialogueviewbase.requestinterrupt.md) | Represents the method that should be called when this view wants the line to be interrupted. |

## Methods

| Name                                                                                          | Description                                                                                                                                                                                    |
| --------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [DialogueComplete()](yarn.unity.dialogueviewbase.dialoguecomplete.md)                         | Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that the dialogue has ended, and no more lines will be delivered.                                                      |
| [DialogueStarted()](yarn.unity.dialogueviewbase.dialoguestarted.md)                           | Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that dialogue has started.                                                                                             |
| [DismissLine(Action)](yarn.unity.dialogueviewbase.dismissline.md)                             | Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that the view should dismiss its current line from display, and clean up.                                              |
| [InterruptLine(LocalizedLine,Action)](yarn.unity.dialogueviewbase.interruptline.md)           | Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that a line has been interrupted, and that the Dialogue View should finish presenting its line as quickly as possible. |
| [RunLine(LocalizedLine,Action)](yarn.unity.dialogueviewbase.runline.md)                       | Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that a line should be displayed to the user.                                                                           |
| [RunOptions(DialogueOption\[\],Action)](yarn.unity.dialogueviewbase.runoptions.md)            | Called by the [DialogueRunner](../yarn.unity.dialoguerunner/) to signal that a set of options should be displayed to the user.                                                                 |
| [UserRequestedViewAdvancement()](yarn.unity.dialogueviewbase.userrequestedviewadvancement.md) | Called by [DialogueAdvanceInput](../yarn.unity.dialogueadvanceinput/) to signal that the user has requested that the dialogue advance.                                                         |

## See Also

* [LineProviderBehaviour](../yarn.unity.lineproviderbehaviour/): A `UnityEngine.MonoBehaviour` that produces [LocalizedLine](../yarn.unity.localizedline/) s, for use in Dialogue Views.
* [DialogueRunner.dialogueViews](../yarn.unity.dialoguerunner/yarn.unity.dialoguerunner.dialogueviews.md): The View classes that will present the dialogue to the user.
