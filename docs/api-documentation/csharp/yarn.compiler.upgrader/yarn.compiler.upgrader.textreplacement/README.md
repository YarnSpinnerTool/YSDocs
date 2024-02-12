# TextReplacement

Struct in [Yarn.Compiler.Upgrader](../)

Inherits from `System.ValueType`

## Summary

Contains information describing a replacement to make in a string.

```csharp
public struct TextReplacement
```

## Fields

| Name                                                                         | Description                                                                                                                                                     |
| ---------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Comment](yarn.compiler.upgrader.textreplacement.comment.md)                 | A descriptive comment explaining why the substitution is necessary.                                                                                             |
| [OriginalText](yarn.compiler.upgrader.textreplacement.originaltext.md)       | The string to expect at [Start](yarn.compiler.upgrader.textreplacement.start.md) in the original string.                                                        |
| [ReplacementText](yarn.compiler.upgrader.textreplacement.replacementtext.md) | The string to replace [OriginalText](yarn.compiler.upgrader.textreplacement.originaltext.md) with at [Start](yarn.compiler.upgrader.textreplacement.start.md) . |
| [Start](yarn.compiler.upgrader.textreplacement.start.md)                     | The position in the original string where the substitution should be made.                                                                                      |
| [StartLine](yarn.compiler.upgrader.textreplacement.startline.md)             | The line in the original string where the substitution should be made.                                                                                          |

## Properties

| Name                                                                             | Description                                                                                           |
| -------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| [OriginalLength](yarn.compiler.upgrader.textreplacement.originallength.md)       | Gets the length of [OriginalText](yarn.compiler.upgrader.textreplacement.originaltext.md) .           |
| [ReplacementLength](yarn.compiler.upgrader.textreplacement.replacementlength.md) | Gets the length of [ReplacementLength](yarn.compiler.upgrader.textreplacement.replacementlength.md) . |
