# YarnStateInjectorAttribute

Class in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from `Attribute`

## Summary


Inject state for any commands in this class using this static method.


```csharp
public class YarnStateInjectorAttribute : Attribute {
    }
```

## Remarks


The method will be expected to take a string, and return an entity
of the same type as the class being operated on. (So, for example,
an injector for  <code>BoxCollider</code>  would take in a string
and find a  <code>BoxCollider</code> .)

By default, Yarn will use  <code>GameObject.Find(string)</code> 
if there is no injector defined. This is fairly inefficient (an
<code>O(n)</code>  lookup), so it is recommended that you restrict your
lookup conditions so that you can find it quicker (eg, a cache).

This injector should be a static function. Non-static functions
will be ignored.


## Properties

|Name|Description|
|:---|:---|
|[Injector](/api/csharp/yarn.unity.yarnstateinjectorattribute.injector.md)|Method to use as an injector.|

