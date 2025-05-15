# MessageBoxAttribute

Class in [Yarn.Unity.Attributes](/docs/api/csharp/yarn.unity.attributes.md)

Inherits from [`YarnEditorAttribute`](/docs/api/csharp/yarn.unity.attributes.yarneditorattribute.md)

## Summary


Shows a message box on the property.


```csharp
public class MessageBoxAttribute : YarnEditorAttribute
```

## Enums

|Name|Description|
|:---|:---|
|[Type](/docs/api/csharp/yarn.unity.attributes.messageboxattribute.type.md)|The type of the message box to display.|

## Methods

|Name|Description|
|:---|:---|
|[Error(string)](/docs/api/csharp/yarn.unity.attributes.messageboxattribute.error.md)|Creates a new error  [Message](yarn.unity.attributes.messageboxattribute.message.md)  using the provided text.|
|[Info(string)](/docs/api/csharp/yarn.unity.attributes.messageboxattribute.info.md)|Creates a new information  [Message](yarn.unity.attributes.messageboxattribute.message.md)  using the provided text.|
|[Neutral(string)](/docs/api/csharp/yarn.unity.attributes.messageboxattribute.neutral.md)|Creates a new neutral  [Message](yarn.unity.attributes.messageboxattribute.message.md)  using the provided text.|
|[Warning(string)](/docs/api/csharp/yarn.unity.attributes.messageboxattribute.warning.md)|Creates a new warning  [Message](yarn.unity.attributes.messageboxattribute.message.md)  using the provided text.|

## Properties

|Name|Description|
|:---|:---|
|[NoMessage](/docs/api/csharp/yarn.unity.attributes.messageboxattribute.nomessage.md)|Returns a new  [Message](yarn.unity.attributes.messageboxattribute.message.md)  that represents an instruction to not draw a message box at all.|
|[SourceMethod](/docs/api/csharp/yarn.unity.attributes.messageboxattribute.sourcemethod.md)|The name of a method that will be called to determine the contents of the message box. The method must return a  [Message](yarn.unity.attributes.messageboxattribute.message.md) .|

## Structs

|Name|Description|
|:---|:---|
|[Message](/docs/api/csharp/yarn.unity.attributes.messageboxattribute.message.md)|A description for a message box to show in the Unity Inspector.|

