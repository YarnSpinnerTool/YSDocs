# Declaration.Range

Property in [Declaration](/docs/api/csharp/yarn.compiler.declaration.md)

## Summary


Gets the range of text at which this declaration occurs.


```csharp
public Range Range { get; internal set; }
```

## Remarks


This range refers to the declaration of the symbol itself, and not
any syntax surrounding it. For example, the declaration
<code>&lt;&lt;declare $x = 1&gt;&gt;</code>  would have a Range referring
to the  <code>$x</code>  symbol.


