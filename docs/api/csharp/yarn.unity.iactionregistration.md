# IActionRegistration

Interface in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

## Summary



```csharp
public interface IActionRegistration
```

## Methods

|Name|Description|
|:---|:---|
|[AddCommandHandler(string,System.Action)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-17.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,Delegate)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-1.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<IEnumerator>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-10.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<Coroutine>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-3.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,MethodInfo)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-2.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-18.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, IEnumerator>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-11.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, Coroutine>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-4.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-19.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, IEnumerator>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-12.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, Coroutine>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-5.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2, T3>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-20.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, IEnumerator>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-13.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, Coroutine>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-6.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2, T3, T4>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-21.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, IEnumerator>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-14.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, Coroutine>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-7.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2, T3, T4, T5>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-22.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, IEnumerator>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-15.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, Coroutine>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-8.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Action<T1, T2, T3, T4, T5, T6>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-23.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, T6, IEnumerator>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-16.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,System.Func<T1, T2, T3, T4, T5, T6, Coroutine>)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-9.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddFunction(string,Delegate)](/docs/api/csharp/yarn.unity.iactionregistration.addfunction-1.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<TResult>)](/docs/api/csharp/yarn.unity.iactionregistration.addfunction-2.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<TResult, T1>)](/docs/api/csharp/yarn.unity.iactionregistration.addfunction-3.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<TResult, T1, T2>)](/docs/api/csharp/yarn.unity.iactionregistration.addfunction-4.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<TResult, T1, T2, T3>)](/docs/api/csharp/yarn.unity.iactionregistration.addfunction-5.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<TResult, T1, T2, T3, T4>)](/docs/api/csharp/yarn.unity.iactionregistration.addfunction-6.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<TResult, T1, T2, T3, T4, T5>)](/docs/api/csharp/yarn.unity.iactionregistration.addfunction-7.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[AddFunction(string,System.Func<TResult, T1, T2, T3, T4, T5, T6>)](/docs/api/csharp/yarn.unity.iactionregistration.addfunction-8.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[RemoveCommandHandler(string)](/docs/api/csharp/yarn.unity.iactionregistration.removecommandhandler.md)|Removes a command handler.|
|[RemoveFunction(string)](/docs/api/csharp/yarn.unity.iactionregistration.removefunction.md)|Remove a registered function.|

