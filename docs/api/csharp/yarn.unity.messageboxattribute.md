# MessageBoxAttribute

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`YarnEditorAttribute`](/docs/api/csharp/yarn.unity.yarneditorattribute.md)

## Summary


Shows a message box on the property.


```csharp
public class MessageBoxAttribute : YarnEditorAttribute
```

## Enums

|Name|Description|
|:---|:---|
|[Type](/docs/api/csharp/yarn.unity.messageboxattribute.type.md)|The type of the message box to display.|

## Methods

|Name|Description|
|:---|:---|
|[Error(string)](/docs/api/csharp/yarn.unity.messageboxattribute.error.md)|Creates a new error  <a href="yarn.unity.messageboxattribute.message.md">Message</a>  using the provided text.|
|[Info(string)](/docs/api/csharp/yarn.unity.messageboxattribute.info.md)|Creates a new information  <a href="yarn.unity.messageboxattribute.message.md">Message</a>  using the provided text.|
|[Neutral(string)](/docs/api/csharp/yarn.unity.messageboxattribute.neutral.md)|Creates a new neutral  <a href="yarn.unity.messageboxattribute.message.md">Message</a>  using the provided text.|
|[Warning(string)](/docs/api/csharp/yarn.unity.messageboxattribute.warning.md)|Creates a new warning  <a href="yarn.unity.messageboxattribute.message.md">Message</a>  using the provided text.|

## Properties

|Name|Description|
|:---|:---|
|[NoMessage](/docs/api/csharp/yarn.unity.messageboxattribute.nomessage.md)|Returns a new  <a href="yarn.unity.messageboxattribute.message.md">Message</a>  that represents an instruction to not draw a message box at all.|
|[SourceMethod](/docs/api/csharp/yarn.unity.messageboxattribute.sourcemethod.md)|The name of a method that will be called to determine the contents of the message box. The method must return a  <a href="yarn.unity.messageboxattribute.message.md">Message</a> .|

## Structs

|Name|Description|
|:---|:---|
|[Message](/docs/api/csharp/yarn.unity.messageboxattribute.message.md)|A description for a message box to show in the Unity Inspector.|

