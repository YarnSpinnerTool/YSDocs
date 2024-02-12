# GetLineInfo(int)

Method in [DebugInfo](./)

## Summary

Gets a [LineInfo](yarn.compiler.debuginfo.lineinfo/) object that describes the specified instruction at the index `instructionNumber` .

```csharp
public LineInfo GetLineInfo(int instructionNumber)
```

## Parameters

| Name                    | Description                                               |
| ----------------------- | --------------------------------------------------------- |
| `int` instructionNumber | The index of the instruction to retrieve information for. |

## Returns

A [LineInfo](yarn.compiler.debuginfo.lineinfo/) object that describes the position of the instruction.
