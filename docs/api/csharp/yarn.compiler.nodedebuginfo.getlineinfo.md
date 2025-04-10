# GetLineInfo(int)

Method in [NodeDebugInfo](yarn.compiler.nodedebuginfo.md)

## Summary

Gets a [LineInfo](yarn.compiler.nodedebuginfo.lineinfo.md) object that describes the specified instruction at the index `instructionNumber` .

```csharp
public LineInfo GetLineInfo(int instructionNumber)
```

## Parameters

| Name                    | Description                                               |
| ----------------------- | --------------------------------------------------------- |
| `int` instructionNumber | The index of the instruction to retrieve information for. |

## Returns

A [LineInfo](yarn.compiler.nodedebuginfo.lineinfo.md) object that describes the position of the instruction.
