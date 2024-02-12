# YarnStateInjectorAttribute

Attribute in [Yarn.Unity](../)

Inherits from `System.Attribute`

## Summary

Inject state for any commands in this class using this static method.

```csharp
public class YarnStateInjectorAttribute : Attribute
```

## Remarks

The method will be expected to take a string, and return an entity of the same type as the class being operated on. (So, for example, an injector for `UnityEngine.BoxCollider` would take in a string and find a `UnityEngine.BoxCollider`.)

By default, Yarn will use `UnityEngine.GameObject.Find(System.String)` if there is no injector defined. This is fairly inefficient (an `O(n)` lookup), so it is recommended that you restrict your lookup conditions so that you can find it quicker (eg, a cache).

This injector should be a static function. Non-static functions will be ignored.

## Properties

| Name                                                          | Description                   |
| ------------------------------------------------------------- | ----------------------------- |
| [Injector](yarn.unity.yarnstateinjectorattribute.injector.md) | Method to use as an injector. |
