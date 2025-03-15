# SetProgram(Program)

Method in [Dialogue](yarn.dialogue.md)

## Summary

Loads all nodes from the provided [Program](yarn.program.md) .

```csharp
public void SetProgram(Program program)
```

## Remarks

This method replaces any existing nodes have been loaded. If you want to load nodes from an _additional_ Program, use the [AddProgram(Program)](yarn.dialogue.addprogram.md) method.

## Parameters

| Name                                    | Description                            |
| --------------------------------------- | -------------------------------------- |
| [Yarn.Program](yarn.program.md) program | The [Program](yarn.program.md) to use. |
