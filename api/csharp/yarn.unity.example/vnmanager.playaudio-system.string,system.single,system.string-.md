# VNManager.PlayAudio Method
PlayAudio( soundName,volume,"loop" )...
PlayAudio(soundName,1.0) plays soundName once at 100% volume...
if third parameter was word "loop" it would loop "volume" is a
number from 0.0 to 1.0 "loop" is the word "loop" (or "true"),
which tells the sound to loop over and over

```csharp
public void PlayAudio(string soundName, float volume = null, string loop = "")
```

## Parameters
|Parameter|Description|
|:---|:---|
|[`string`](https://docs.microsoft.com/dotnet/api/System.String) soundName||
|[`float`](https://docs.microsoft.com/dotnet/api/System.Single) volume||
|[`string`](https://docs.microsoft.com/dotnet/api/System.String) loop||


<div class="class-metadata">

Parent: [`VNManager`](/api/csharp/yarn.unity.example/vnmanager.md), Namespace: [`Yarn.Unity.Example`](/api/csharp/yarn.unity.example/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Samples~/VisualNovel/Scripts/VNManager.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Samples~/VisualNovel/Scripts/VNManager.cs#L267), line 267.
