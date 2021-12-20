# RegisterFunction(string,Func<T1, T2, TResult>)

Method in [Library](/api/csharp/yarn.library.md)

## Summary


Registers a new function that returns a value, which can be
called from a Yarn program.


```csharp
public void RegisterFunction<T1, T2, TResult>(string name, Func<T1, T2, TResult> implementation)
```

