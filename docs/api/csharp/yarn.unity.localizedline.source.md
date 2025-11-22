# LocalizedLine.Source

Field in [LocalizedLine](/docs/api/csharp/yarn.unity.localizedline.md)

## Summary


The object that created this line.
Most of the time will be the  <code>DialogueRuner</code>  that passed the presenter the line.


```csharp
public object? Source;
```

## Remarks


This exists for situations where you need the dialogue runner (or your custom equivalent) to send back messages.
In particular this is used by the  <a href="yarn.unity.voiceoverpresenter.md">VoiceOverPresenter</a>  to get a reference to the dialogue runner to advance lines after playback is finished without needing a specific reference.
Allowing the presenter to be reused across multiple runners.


