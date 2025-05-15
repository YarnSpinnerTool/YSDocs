# Node.ContentSaliencyConditionVariables

Property in [Node](/docs/api/csharp/yarn.node.md)

## Summary


Gets an enumerable containing the names of variables that must be
evaluated in order to determine whether this node can be selected as
a piece of salient content.


```csharp
public IEnumerable<string> ContentSaliencyConditionVariables
{
            get; }
```

## Remarks


The list of variables is stored in the header as a
semicolon-delimited string.


