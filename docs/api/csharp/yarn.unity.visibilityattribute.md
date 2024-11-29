# VisibilityAttribute

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`YarnEditorAttribute`](/docs/api/csharp/yarn.unity.yarneditorattribute.md)

## Summary


Controls whether a property is visible or not in the Unity Inspector.


```csharp
public abstract class VisibilityAttribute : YarnEditorAttribute
```

## Enums

|Name|Description|
|:---|:---|
|[AttributeMode](/docs/api/csharp/yarn.unity.visibilityattribute.attributemode.md)|The type of test represented by  <a href="yarn.unity.visibilityattribute.condition.md">Condition</a> .|

## Properties

|Name|Description|
|:---|:---|
|[Condition](/docs/api/csharp/yarn.unity.visibilityattribute.condition.md)|The name of another property on the object that determines whether this property is visible or not.|
|[EnumValue](/docs/api/csharp/yarn.unity.visibilityattribute.enumvalue.md)|The value that the variable indicated by  <a href="yarn.unity.visibilityattribute.condition.md">Condition</a>  is compared to.|
|[Invert](/docs/api/csharp/yarn.unity.visibilityattribute.invert.md)|Controls whether the property appears when the condition passes ( <code>true</code> ), or fails ( <code>false</code> ).|
|[Mode](/docs/api/csharp/yarn.unity.visibilityattribute.mode.md)|The type of test that  <a href="yarn.unity.visibilityattribute.condition.md">Condition</a>  represents.|

