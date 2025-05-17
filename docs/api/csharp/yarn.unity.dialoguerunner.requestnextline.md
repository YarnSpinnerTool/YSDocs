# DialogueRunner.RequestNextLine()

Method in [DialogueRunner](/docs/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


Requests that all dialogue views stop showing the current line, and
prepare to show the next piece of content.


```csharp
public void RequestNextLine()
```

## Remarks

<p>
The specific behaviour of what happens when this method is called
depends on the implementation of the Dialogue Runner's current
dialogue views.
</p> <p>
If the dialogue runner is not currently running a line (for example,
if it is running options, or is not running dialogue at all), this
method has no effect.
</p>

