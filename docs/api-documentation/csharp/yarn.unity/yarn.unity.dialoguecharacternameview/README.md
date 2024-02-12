# DialogueCharacterNameView

Class in [Yarn.Unity](../)

Inherits from [`DialogueViewBase`](../yarn.unity.dialogueviewbase/)

## Summary

A subclass of [DialogueViewBase](../yarn.unity.dialogueviewbase/) that displays character names.

```csharp
public class DialogueCharacterNameView : Yarn.Unity.DialogueViewBase
```

## Remarks

This class uses the `character` attribute on lines that it receives to determine its content. When the view's [RunLine(LocalizedLine,Action)](yarn.unity.dialoguecharacternameview.runline.md) method is called with a line whose [Text](../yarn.unity.localizedline/yarn.unity.localizedline.text.md) contains a `character` attribute, the [onNameUpdate](yarn.unity.dialoguecharacternameview.onnameupdate.md) event is fired. If the line does not contain such an attribute, the [onNameNotPresent](yarn.unity.dialoguecharacternameview.onnamenotpresent.md) event is fired instead.

This view does not present any options or handle commands. It's intended to be used alongside other subclasses of DialogueViewBase.

## Fields

| Name                                                                           | Description                                                                                         |
| ------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------- |
| [onDialogueStarted](yarn.unity.dialoguecharacternameview.ondialoguestarted.md) | Invoked when the dialogue is started.                                                               |
| [onNameNotPresent](yarn.unity.dialoguecharacternameview.onnamenotpresent.md)   | Invoked when a line is received that doesn't contain a character name.                              |
| [onNameUpdate](yarn.unity.dialoguecharacternameview.onnameupdate.md)           | Invoked when a line is received that contains a character name. The name is given as the parameter. |

## Methods

| Name                                                                             | Description |
| -------------------------------------------------------------------------------- | ----------- |
| [DialogueStarted()](yarn.unity.dialoguecharacternameview.dialoguestarted.md)     |             |
| [RunLine(LocalizedLine,Action)](yarn.unity.dialoguecharacternameview.runline.md) |             |

## See Also

* DialogueUI
