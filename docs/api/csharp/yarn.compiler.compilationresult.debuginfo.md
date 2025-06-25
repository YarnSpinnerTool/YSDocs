# DebugInfo

Property in [CompilationResult](yarn.compiler.compilationresult.md)

{% hint style="warning" %}
This property is obsolete and may be removed from a future version of Yarn Spinner: Use ProjectDebugInfo.Nodes.
{% endhint %}

## Summary

Gets the collection of [DebugInfo](yarn.compiler.compilationresult.debuginfo.md) objects for each node\
in [Program](yarn.compiler.compilationresult.program.md) .

```csharp
public IReadOnlyDictionary<string, NodeDebugInfo> DebugInfo { get }
```
