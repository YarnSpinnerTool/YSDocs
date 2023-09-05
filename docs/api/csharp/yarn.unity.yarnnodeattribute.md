# YarnNodeAttribute

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `UnityEngine.PropertyAttribute`

## Summary


Specifies that a field represents a reference to a named Yarn node that
exists in a Yarn project.


```csharp
public class YarnNodeAttribute : PropertyAttribute
```

## Remarks

<p>
This attribute causes the inspector to draw a popup that allows
selecting a node from a list of all nodes available in a Yarn project.
</p> <p>
This attribute may only be used with <code>string</code> fields.
</p>

## Fields

|Name|Description|
|:---|:---|
|[yarnProjectAttribute](/docs/api/csharp/yarn.unity.yarnnodeattribute.yarnprojectattribute.md)|The name of a property that specifies the YarnProject containing the desired node.|

