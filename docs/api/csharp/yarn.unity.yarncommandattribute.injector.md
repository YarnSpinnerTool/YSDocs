# YarnCommandAttribute.Injector

Property in [YarnCommandAttribute](/docs/api/csharp/yarn.unity.yarncommandattribute.md)

## Summary


Override the state injector for this command only.


```csharp
public string Injector { get; set; }
```

## Remarks

<p>
If not defined, will use the method marked by <a href="yarn.unity.yarnstateinjectorattribute.md">YarnStateInjectorAttribute</a> on the class, or if that is not
defined and the class subclasses <code>UnityEngine.MonoBehaviour</code>, using
<code>UnityEngine.GameObject.Find(System.String)</code>.
</p> <p>
If none of those conditions are true, but the function is not
static, an error will be thrown. However, if the function is indeed
static, this parameter will be ignored.
</p>

