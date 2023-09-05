# DialogueCharacterNameView

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`DialogueViewBase`](/docs/api/csharp/yarn.unity.dialogueviewbase.md)

## Summary


A subclass of  <a href="yarn.unity.dialogueviewbase.md">DialogueViewBase</a>  that displays
character names.


```csharp
public class DialogueCharacterNameView : Yarn.Unity.DialogueViewBase
```

## Remarks


This class uses the `character` attribute on lines that it receives
to determine its content. When the view's  <a href="yarn.unity.dialoguecharacternameview.runline.md">RunLine(LocalizedLine,Action)</a> 
method is called with a line whose  <a href="yarn.unity.localizedline.text.md">Text</a> 
contains a `character` attribute, the  <a href="yarn.unity.dialoguecharacternameview.onnameupdate.md">onNameUpdate</a> 
event is fired. If the line does not contain such an attribute, the
<a href="yarn.unity.dialoguecharacternameview.onnamenotpresent.md">onNameNotPresent</a>  event is fired instead.

This view does not present any options or handle commands. It's
intended to be used alongside other subclasses of DialogueViewBase.


## Fields

|Name|Description|
|:---|:---|
|[onDialogueStarted](/docs/api/csharp/yarn.unity.dialoguecharacternameview.ondialoguestarted.md)|Invoked when the dialogue is started.|
|[onNameNotPresent](/docs/api/csharp/yarn.unity.dialoguecharacternameview.onnamenotpresent.md)|Invoked when a line is received that doesn't contain a character name.|
|[onNameUpdate](/docs/api/csharp/yarn.unity.dialoguecharacternameview.onnameupdate.md)|Invoked when a line is received that contains a character name. The name is given as the parameter.|

## Methods

|Name|Description|
|:---|:---|
|[DialogueStarted()](/docs/api/csharp/yarn.unity.dialoguecharacternameview.dialoguestarted.md)||
|[RunLine(LocalizedLine,Action)](/docs/api/csharp/yarn.unity.dialoguecharacternameview.runline.md)||

## See Also

* DialogueUI

