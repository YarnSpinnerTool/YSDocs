# Compiler.FlattenParseTree(IParseTree)

Method in [Compiler](/docs/api/csharp/yarn.compiler.compiler.md)

## Summary


Flattens a tree of  `Antlr4.Runtime.Tree.IParseTree`  objects by
recursively visiting their children, and converting them into a
flat  `System.Collections.Generic.IEnumerable`1` .


```csharp
public static IEnumerable<IParseTree> FlattenParseTree(IParseTree node)
```

## Parameters

|Name|Description|
|:---|:---|
|`Antlr4.Runtime.Tree.IParseTree` node|The root node to begin work from.|

## Returns

An  `System.Collections.Generic.IEnumerable`1`  that contains a
flattened version of the hierarchy rooted at  `node` .

