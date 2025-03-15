# Injector

Property in [YarnCommandAttribute](yarn.unity.yarncommandattribute.md)

## Summary

Override the state injector for this command only.

```csharp
public string Injector { get; set; }
```

## Remarks

If not defined, will use the method marked by [YarnStateInjectorAttribute](yarn.unity.yarnstateinjectorattribute.md) on the class, or if that is not defined and the class subclasses `UnityEngine.MonoBehaviour`, using `UnityEngine.GameObject.Find(System.String)`.

If none of those conditions are true, but the function is not static, an error will be thrown. However, if the function is indeed static, this parameter will be ignored.
