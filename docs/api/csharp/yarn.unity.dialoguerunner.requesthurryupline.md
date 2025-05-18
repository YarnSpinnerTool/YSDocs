# DialogueRunner.RequestHurryUpLine()

Method in [DialogueRunner](/docs/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


Requests that all dialogue presenters speed up their delivery of the
current line.


```csharp
public void RequestHurryUpLine()
```

## Remarks

<p>
The specific behaviour of what happens when this method is called
depends on the implementation of the Dialogue Runner's current
dialogue presenters.
</p> <p>
If the dialogue runner is not currently running a line (for example,
if it is running options, or is not running dialogue at all), this
method has no effect.
</p>

