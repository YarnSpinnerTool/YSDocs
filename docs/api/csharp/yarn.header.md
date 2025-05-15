# Header

Class in [Yarn](broken-reference)

Inherits from `System.Object`

## Summary

```csharp
public sealed class Header : pb::IMessage<Header>
#if !GOOGLE_PROTOBUF_REFSTRUCT_COMPATIBILITY_MODE
      , pb::IBufferMessage
```

## Constructors

| Name                                     | Description |
| ---------------------------------------- | ----------- |
| [Header()](yarn.header..ctor-1.md)       |             |
| [Header(Header)](yarn.header..ctor-2.md) |             |

## Fields

| Name                                                | Description                         |
| --------------------------------------------------- | ----------------------------------- |
| [KeyFieldNumber](yarn.header.keyfieldnumber.md)     | Field number for the "key" field.   |
| [ValueFieldNumber](yarn.header.valuefieldnumber.md) | Field number for the "value" field. |

## Methods

| Name                                                          | Description |
| ------------------------------------------------------------- | ----------- |
| [CalculateSize()](yarn.header.calculatesize.md)               |             |
| [Clone()](yarn.header.clone.md)                               |             |
| [Equals(object)](yarn.header.equals-1.md)                     |             |
| [Equals(Header)](yarn.header.equals-2.md)                     |             |
| [GetHashCode()](yarn.header.gethashcode.md)                   |             |
| [MergeFrom(pb::CodedInputStream)](yarn.header.mergefrom-2.md) |             |
| [MergeFrom(Header)](yarn.header.mergefrom-1.md)               |             |
| [ToString()](yarn.header.tostring.md)                         |             |
| [WriteTo(pb::CodedOutputStream)](yarn.header.writeto.md)      |             |

## Properties

| Name                                    | Description              |
| --------------------------------------- | ------------------------ |
| [Descriptor](yarn.header.descriptor.md) |                          |
| [Key](yarn.header.key.md)               | The name of the header.  |
| [Parser](yarn.header.parser.md)         |                          |
| [Value](yarn.header.value.md)           | The value of the header. |
