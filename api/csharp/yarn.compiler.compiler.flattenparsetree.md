# FlattenParseTree(IParseTree)

Method in [Compiler](/api/csharp/yarn.compiler.compiler.md)

## Summary


Flattens a tree of  <code>T:Antlr4.Runtime.Tree.IParseTree</code>  objects by
recursively visiting their children, and converting them into a
flat  <code>T:System.Collections.Generic.IEnumerable`1</code> .


```csharp
public static IEnumerable<IParseTree> FlattenParseTree(IParseTree node)
```

## Parameters

|Name|Description|
|:---|:---|
|node|The root node to begin work from.|

## Returns

An  <code>T:System.Collections.Generic.IEnumerable`1</code>  that contains a
flattened version of the hierarchy rooted at  <code>node</code> .

