# LineStatus.Interrupted Field

The line got interrupted while being build up and should
complete showing the line asap. View classes should get to the
end of the line as fast as possible. A view class showing text
would stop building up the text and immediately show the entire
line and a view class playing voice over clips would do a very
quick fade out and stop playback afterwards.


```csharp
Interrupted = 1
```



## See Also
* [`LineStatus`](/api/csharp/yarn.unity/linestatus.md): 
The presentation status of a [`LocalizedLine`](/api/csharp/yarn.unity/localizedline.md).

## Namespace
[`Yarn.Unity`](/api/csharp/yarn.unity/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/DialogueRunner.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/DialogueRunner.cs#L1466), line 1466.
