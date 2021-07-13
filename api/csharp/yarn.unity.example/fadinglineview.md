# FadingLineView Class

A dialogue view that presents lines in a <see cref="!:Text"></see>
component, and options in a vertical list. The text fades in from
transparency when delivering a line, and fades out when the line is
complete. Each character can have a custom colour to use. In
addition, pressing the Spacebar key will skip the line.


```csharp
public class FadingLineView : DialogueViewBase
```



## Methods
|Name|Description|
|:---|:---|
|[`DismissLine(Action)`](/api/csharp/yarn.unity.example/fadinglineview.dismissline-action-.md)||
|[`DismissLine(Action)`](/api/csharp/yarn.unity.example/fadinglineview.dismissline-action-.md)||
|[`GetColorForCharacter(String)`](/api/csharp/yarn.unity.example/fadinglineview.getcolorforcharacter-system.string-.md)| Returns a Color to use for a line, based on the name of the character.  |
|[`GetColorForCharacter(String)`](/api/csharp/yarn.unity.example/fadinglineview.getcolorforcharacter-system.string-.md)| Returns a Color to use for a line, based on the name of the character.  |
|[`OnLineStatusChanged(LocalizedLine)`](/api/csharp/yarn.unity.example/fadinglineview.onlinestatuschanged-yarn.unity.localizedline-.md)||
|[`OnLineStatusChanged(LocalizedLine)`](/api/csharp/yarn.unity.example/fadinglineview.onlinestatuschanged-yarn.unity.localizedline-.md)||
|[`OptionButtonSelected(Int32, Action<Int32>)`](/api/csharp/yarn.unity.example/fadinglineview.optionbuttonselected-system.int32,action-system.int32--.md)||
|[`OptionButtonSelected(Int32, Action<Int32>)`](/api/csharp/yarn.unity.example/fadinglineview.optionbuttonselected-system.int32,action-system.int32--.md)||
|[`RunLine(LocalizedLine, Action)`](/api/csharp/yarn.unity.example/fadinglineview.runline-yarn.unity.localizedline,action-.md)||
|[`RunLine(LocalizedLine, Action)`](/api/csharp/yarn.unity.example/fadinglineview.runline-yarn.unity.localizedline,action-.md)||
|[`RunOptions(DialogueOption[], Action<Int32>)`](/api/csharp/yarn.unity.example/fadinglineview.runoptions-yarn.unity.dialogueoption--,action-system.int32--.md)||
|[`RunOptions(DialogueOption[], Action<Int32>)`](/api/csharp/yarn.unity.example/fadinglineview.runoptions-yarn.unity.dialogueoption--,action-system.int32--.md)||
## Namespace
[`Yarn.Unity.Example`](/api/csharp/yarn.unity.example/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Samples~/StartHere/Scripts/FadingLineView.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Samples~/StartHere/Scripts/FadingLineView.cs#L20), line 20.
