# YarnStateInjectorAttribute

Attribute in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from `System.Attribute`

## Summary


Inject state for any commands in this class using this static method.


```csharp
public class YarnStateInjectorAttribute : Attribute
```

## Remarks

<p>
The method will be expected to take a string, and return an entity
of the same type as the class being operated on. (So, for example,
an injector for <code>UnityEngine.BoxCollider</code> would take in a string
and find a <code>UnityEngine.BoxCollider</code>.)
</p> <p>
By default, Yarn will use <code>UnityEngine.GameObject.Find(System.String)</code>
if there is no injector defined. This is fairly inefficient (an
<code>O(n)</code> lookup), so it is recommended that you restrict your
lookup conditions so that you can find it quicker (eg, a cache).
</p> <p>
This injector should be a static function. Non-static functions
will be ignored.
</p>

## Properties

|Name|Description|
|:---|:---|
|[Injector](/api/csharp/yarn.unity.yarnstateinjectorattribute.injector.md)|Method to use as an injector.|

