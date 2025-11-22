# IActionRegistration.AddFunction(string,Delegate)

Method in [IActionRegistration](/docs/api/csharp/yarn.unity.iactionregistration.md)

## Summary


Add a new function that returns a value, so that it can be called
from Yarn scripts.


```csharp
void AddFunction(string name, Delegate implementation);
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
|`Delegate` implementation|The  <code>System.Delegate</code>  that should be invoked when this function is called.|

## See Also

* [Library](/docs/api/csharp/yarn.library.md): A collection of functions that can be called from Yarn programs.

