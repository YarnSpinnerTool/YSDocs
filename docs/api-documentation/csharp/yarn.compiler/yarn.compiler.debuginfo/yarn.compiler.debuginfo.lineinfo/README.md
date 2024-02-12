# LineInfo

Struct in [DebugInfo](../)

Inherits from `System.ValueType`

## Summary

Contains positional information about an instruction.

```csharp
public struct LineInfo
```

## Fields

| Name                                                                   | Description                                                                                                                                                               |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [CharacterNumber](yarn.compiler.debuginfo.lineinfo.characternumber.md) | The zero-indexed character number in [FileName](yarn.compiler.debuginfo.lineinfo.filename.md) that contains the statement or expression that this line was produced from. |
| [FileName](yarn.compiler.debuginfo.lineinfo.filename.md)               | The file name of the source that this intruction was produced from.                                                                                                       |
| [LineNumber](yarn.compiler.debuginfo.lineinfo.linenumber.md)           | The zero-indexed line number in [FileName](yarn.compiler.debuginfo.lineinfo.filename.md) that contains the statement or expression that this line was produced from.      |
| [NodeName](yarn.compiler.debuginfo.lineinfo.nodename.md)               | The node name of the source that this intruction was produced from.                                                                                                       |
