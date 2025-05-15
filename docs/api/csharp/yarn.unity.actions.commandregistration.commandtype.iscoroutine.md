# CommandType.IsCoroutine

## Summary


The method returns  `System.Collections.IEnumerator`  (that is, it is
a coroutine).


```csharp
IsCoroutine
```

## Remarks


Code that invokes this command should use  `UnityEngine.MonoBehaviour.StartCoroutine(System.Collections.IEnumerator)`  to begin
the coroutine.


