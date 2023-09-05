# TextReplacement

Struct in [Yarn.Compiler.Upgrader](/api/csharp/yarn.compiler.upgrader.md)

Inherits from `System.ValueType`

## Summary


Contains information describing a replacement to make in a string.


```csharp
public struct TextReplacement
```

## Fields

|Name|Description|
|:---|:---|
|[Comment](/api/csharp/yarn.compiler.upgrader.textreplacement.comment.md)|A descriptive comment explaining why the substitution is necessary.|
|[OriginalText](/api/csharp/yarn.compiler.upgrader.textreplacement.originaltext.md)|The string to expect at  <a href="yarn.compiler.upgrader.textreplacement.start.md">Start</a>  in the original string.|
|[ReplacementText](/api/csharp/yarn.compiler.upgrader.textreplacement.replacementtext.md)|The string to replace  <a href="yarn.compiler.upgrader.textreplacement.originaltext.md">OriginalText</a>  with at  <a href="yarn.compiler.upgrader.textreplacement.start.md">Start</a> .|
|[Start](/api/csharp/yarn.compiler.upgrader.textreplacement.start.md)|The position in the original string where the substitution should be made.|
|[StartLine](/api/csharp/yarn.compiler.upgrader.textreplacement.startline.md)|The line in the original string where the substitution should be made.|

## Properties

|Name|Description|
|:---|:---|
|[OriginalLength](/api/csharp/yarn.compiler.upgrader.textreplacement.originallength.md)|Gets the length of  <a href="yarn.compiler.upgrader.textreplacement.originaltext.md">OriginalText</a> .|
|[ReplacementLength](/api/csharp/yarn.compiler.upgrader.textreplacement.replacementlength.md)|Gets the length of  <a href="yarn.compiler.upgrader.textreplacement.replacementlength.md">ReplacementLength</a> .|

