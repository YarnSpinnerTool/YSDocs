# TypeBase.IsConvertibleTo(TypeBase)

Method in [TypeBase](/docs/api/csharp/yarn.typebase.md)

## Summary


Checks if this type is convertible to the type represented by
<code>otherType</code> .


```csharp
public bool IsConvertibleTo(TypeBase otherType)
```

## Remarks


A type is convertible to another type if: 
<ol type="number">
<li>there is an explicit conversion available, or</li>
<li>it is a descendant of that type, or</li>
<li>
the two types are identical.</li>
</ol>

## Parameters

|Name|Description|
|:---|:---|
|[Yarn.TypeBase](/docs/api/csharp/yarn.typebase.md) otherType|The type to check.|

## Returns

<code>true</code>  if this type is convertible to
<code>otherType</code> .

