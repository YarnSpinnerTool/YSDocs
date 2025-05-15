# AttributeMode

Enum in [VisibilityAttribute](/docs/api/csharp/yarn.unity.attributes.visibilityattribute.md)

Inherits from `System.Enum`

## Summary


The type of test represented by  [Condition](yarn.unity.attributes.visibilityattribute.condition.md) .


```csharp
public enum AttributeMode
{
    BooleanCondition,
    EnumEquality
}
```

## Members

|Name|Description|
|:---|:---|
|[BooleanCondition](/docs/api/csharp/yarn.unity.attributes.visibilityattribute.attributemode.booleancondition.md)|[Condition](yarn.unity.attributes.visibilityattribute.condition.md)  is the name of a  `bool`  variable or a reference to a  `UnityEngine.Object` , and the test passes when the variable is  `true`  (if bool) or non-null (if an object).|
|[EnumEquality](/docs/api/csharp/yarn.unity.attributes.visibilityattribute.attributemode.enumequality.md)|[Condition](yarn.unity.attributes.visibilityattribute.condition.md)  is the name of an enum variable, and the test passes when the variable's value is equal to  [EnumValue](yarn.unity.attributes.visibilityattribute.enumvalue.md) .|

