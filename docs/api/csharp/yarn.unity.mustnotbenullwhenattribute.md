# MustNotBeNullWhenAttribute

Class in [Yarn.Unity](yarn.unity.md)

Inherits from [`YarnEditorAttribute`](yarn.unity.yarneditorattribute.md)

## Summary

Shows an error message box if this property is null and the variable indicated by [Condition](yarn.unity.mustnotbenullwhenattribute.condition.md) is false.

```csharp
public class MustNotBeNullWhenAttribute : YarnEditorAttribute
```

## Properties

| Name                                                            | Description                                                                                                                                   |
| --------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| [Condition](yarn.unity.mustnotbenullwhenattribute.condition.md) | The name of another property on this object to compare to. This variable must be either a boolean value, or a `UnityEngine.Object` reference. |
| [Label](yarn.unity.mustnotbenullwhenattribute.label.md)         | The text of the error message to show if the property is null and the condition is met. If not provided, a generic error message is shown.    |
