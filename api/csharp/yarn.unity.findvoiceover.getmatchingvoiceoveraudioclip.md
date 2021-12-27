# FindVoiceOver.GetMatchingVoiceOverAudioClip(string,string)

Method in [FindVoiceOver](/api/csharp/yarn.unity.findvoiceover.md)

## Summary


Finds all voice over  <code>AudioClip</code> s in the project
with a filename matching a Yarn linetag and a language ID.


```csharp
public static string[] GetMatchingVoiceOverAudioClip(string linetag, string language)
```

## Parameters

|Name|Description|
|:---|:---|
|linetag|The linetag/string ID the voice over filename should match.|
|language|The language ID the voice over filename should match.|

## Returns

A string array with GUIDs of all matching  <code>AudioClip</code> s.

