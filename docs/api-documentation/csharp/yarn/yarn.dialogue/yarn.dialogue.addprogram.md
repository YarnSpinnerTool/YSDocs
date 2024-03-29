# AddProgram(Program)

Method in [Dialogue](./)

## Summary

Loads the nodes from the specified [Program](../yarn.program/) , and adds them to the nodes already loaded.

```csharp
public void AddProgram(Program program)
```

## Remarks

If `Yarn.Dialogue.Program` is `null` , this method has the effect as calling [SetProgram(Program)](yarn.dialogue.setprogram.md) .

## Parameters

| Name                                     | Description                     |
| ---------------------------------------- | ------------------------------- |
| [Yarn.Program](../yarn.program/) program | The additional program to load. |
