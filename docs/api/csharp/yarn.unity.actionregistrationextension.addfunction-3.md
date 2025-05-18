# ActionRegistrationExtension.AddFunction<T1, T2, TResult>(IActionRegistration,string,System.Func<T1, T2, TResult>)

Method in [ActionRegistrationExtension](/docs/api/csharp/yarn.unity.actionregistrationextension.md)

## Summary


Add a new function that returns a value, so that it can be called
from Yarn scripts.


```csharp
public static void AddFunction<T1, T2, TResult>(this IActionRegistration registration, string name, System.Func<T1, T2, TResult> implementation);
```

## Remarks

<p>When this function has been registered, it can be called from
your Yarn scripts like so:</p> <pre lang="yarn">
&lt;&lt;if myFunction(1, 2) == true&gt;&gt;
myFunction returned true!
&lt;&lt;endif&gt;&gt;
</pre> <p>The <code>call</code> command can also be used to invoke the function:</p> <pre lang="yarn">
&lt;&lt;call myFunction(1, 2)&gt;&gt;
</pre>

## Parameters

|Name|Description|
|:---|:---|
|`string` name|The name of the function to add.|
|`Func<T1, T2, TResult>` implementation|The  <code>System.Delegate</code>  that should be invoked when this function is called.|
|[Yarn.Unity.IActionRegistration](/docs/api/csharp/yarn.unity.iactionregistration.md) registration||

## Type Parameters

|Name|Description|
|:---|:---|
|TResult|The result of the function.|

## See Also

* [Library](/docs/api/csharp/yarn.library.md): A collection of functions that can be called from Yarn programs.

