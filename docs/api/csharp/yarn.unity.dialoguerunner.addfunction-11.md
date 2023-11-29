# DialogueRunner.AddFunction(string,System.Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, TResult>)

Method in [DialogueRunner](/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


Add a new function that returns a value, so that it can be
called from Yarn scripts.


```csharp
public void AddFunction<T1, T2, T3, T4, T5, T6, T7, T8, T9, TResult>(string name, System.Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, TResult> implementation);
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
|`Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, TResult>` implementation|The  <code>System.Delegate</code>  that should be invoked when this function is called.|
|`string` name||

## Type Parameters

|Name|Description|
|:---|:---|
|TResult|The type of the value that the function should return.|
|T1|The type of the first parameter to the function.|
|T2|The type of the second parameter to the function.|
|T3|The type of the third parameter to the function.|
|T4|The type of the fourth parameter to the function.|
|T5|The type of the fifth parameter to the function.|
|T6|The type of the sixth parameter to the function.|
|T7|The type of the seventh parameter to the function.|
|T8|The type of the eighth parameter to the function.|
|T9|The type of the ninth parameter to the function.|

## See Also

* [Library](/api/csharp/yarn.library.md): A collection of functions that can be called from Yarn programs.

