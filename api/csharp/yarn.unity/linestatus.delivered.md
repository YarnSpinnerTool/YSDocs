# LineStatus.Delivered Field

The line has been fully presented to the user. A view class
presenting the line as text would be showing the entire line
and a view class playing voice over clips would be silent now.


```csharp
Delivered = 2
```
## Remarks

A line that was previously [`Interrupted`](/api/csharp/yarn.unity/linestatus.interrupted.md)
will become [`Delivered`](/api/csharp/yarn.unity/linestatus.delivered.md) once the [`DialogueViewBase`](/api/csharp/yarn.unity/dialogueviewbase.md) has completed the interruption
process.




## See Also
* [`LineStatus`](/api/csharp/yarn.unity/linestatus.md): 
The presentation status of a [`LocalizedLine`](/api/csharp/yarn.unity/localizedline.md).

## Namespace
[`Yarn.Unity`](/api/csharp/yarn.unity/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/DialogueRunner.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/DialogueRunner.cs#L1478), line 1478.
