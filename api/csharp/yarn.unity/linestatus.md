# LineStatus Enum

The presentation status of a [`LocalizedLine`](/api/csharp/yarn.unity/localizedline.md).


```csharp
public enum LineStatus : int
```



## Fields
|Name|Description|
|:---|:---|
|[`Delivered`](/api/csharp/yarn.unity/linestatus.delivered.md)| The line has been fully presented to the user. A view class presenting the line as text would be showing the entire line and a view class playing voice over clips would be silent now. |
|[`Ended`](/api/csharp/yarn.unity/linestatus.ended.md)| The line is not being presented anymore in any way to the user. |
|[`Interrupted`](/api/csharp/yarn.unity/linestatus.interrupted.md)| The line got interrupted while being build up and should complete showing the line asap. View classes should get to the end of the line as fast as possible. A view class showing text would stop building up the text and immediately show the entire line and a view class playing voice over clips would do a very quick fade out and stop playback afterwards. |
|[`Running`](/api/csharp/yarn.unity/linestatus.running.md)| The line is being build up and shown to the user. |
## Namespace
[`Yarn.Unity`](/api/csharp/yarn.unity/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/DialogueRunner.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/DialogueRunner.cs#L1452), line 1452.
