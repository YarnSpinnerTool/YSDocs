# CommandType.IsCoroutine

## Summary


The method returns  <code>System.Collections.IEnumerator</code>  (that is, it is
a coroutine).


```csharp
IsCoroutine
```

## Remarks


Code that invokes this command should use  <code>UnityEngine.MonoBehaviour.StartCoroutine(System.Collections.IEnumerator)</code>  to begin
the coroutine.


