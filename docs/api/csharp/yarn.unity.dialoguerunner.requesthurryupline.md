# RequestHurryUpLine()

Method in [DialogueRunner](yarn.unity.dialoguerunner.md)

## Summary

Requests that all dialogue presenters speed up their delivery of the\
current line.

```csharp
public void RequestHurryUpLine()
```

## Remarks

The specific behaviour of what happens when this method is called\
depends on the implementation of the Dialogue Runner's current\
dialogue presenters.

If the dialogue runner is not currently running a line (for example,\
if it is running options, or is not running dialogue at all), this\
method has no effect.
