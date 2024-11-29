# AttributeMode

Enum in [VisibilityAttribute](/docs/api/csharp/yarn.unity.visibilityattribute.md)

Inherits from `System.Enum`

## Summary


The type of test represented by  <a href="yarn.unity.visibilityattribute.condition.md">Condition</a> .


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
|[BooleanCondition](/docs/api/csharp/yarn.unity.visibilityattribute.attributemode.booleancondition.md)|<a href="yarn.unity.visibilityattribute.condition.md">Condition</a>  is the name of a  <code>bool</code>  variable or a reference to a  <code>UnityEngine.Object</code> , and the test passes when the variable is  <code>true</code>  (if bool) or non-null (if an object).|
|[EnumEquality](/docs/api/csharp/yarn.unity.visibilityattribute.attributemode.enumequality.md)|<a href="yarn.unity.visibilityattribute.condition.md">Condition</a>  is the name of an enum variable, and the test passes when the variable's value is equal to  <a href="yarn.unity.visibilityattribute.enumvalue.md">EnumValue</a> .|

