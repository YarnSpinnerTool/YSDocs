# CommandType.IsCoroutine

## Summary


The method returns  <code>IEnumerator</code>  (that is, it is
a coroutine).


```csharp
IsCoroutine
```

## Remarks


Code that invokes this command should use  <code>MonoBehaviour.StartCoroutine(IEnumerator)</code>  to begin
the coroutine.


