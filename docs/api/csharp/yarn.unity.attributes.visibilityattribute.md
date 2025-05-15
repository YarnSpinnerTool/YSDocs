# VisibilityAttribute

Class in [Yarn.Unity.Attributes](/docs/api/csharp/yarn.unity.attributes.md)

Inherits from [`YarnEditorAttribute`](/docs/api/csharp/yarn.unity.attributes.yarneditorattribute.md)

## Summary


Controls whether a property is visible or not in the Unity Inspector.


```csharp
public abstract class VisibilityAttribute : YarnEditorAttribute
```

## Enums

|Name|Description|
|:---|:---|
|[AttributeMode](/docs/api/csharp/yarn.unity.attributes.visibilityattribute.attributemode.md)|The type of test represented by  [Condition](yarn.unity.attributes.visibilityattribute.condition.md) .|

## Properties

|Name|Description|
|:---|:---|
|[Condition](/docs/api/csharp/yarn.unity.attributes.visibilityattribute.condition.md)|The name of another property on the object that determines whether this property is visible or not.|
|[EnumValue](/docs/api/csharp/yarn.unity.attributes.visibilityattribute.enumvalue.md)|The value that the variable indicated by  [Condition](yarn.unity.attributes.visibilityattribute.condition.md)  is compared to.|
|[Invert](/docs/api/csharp/yarn.unity.attributes.visibilityattribute.invert.md)|Controls whether the property appears when the condition passes ( `true` ), or fails ( `false` ).|
|[Mode](/docs/api/csharp/yarn.unity.attributes.visibilityattribute.mode.md)|The type of test that  [Condition](yarn.unity.attributes.visibilityattribute.condition.md)  represents.|

