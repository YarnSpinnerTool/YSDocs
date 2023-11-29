# Actions

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `System.Object`

## Summary



```csharp
public class Actions : ICommandDispatcher
```

## Constructors

|Name|Description|
|:---|:---|
|[Actions(DialogueRunner,Library)](/docs/api/csharp/yarn.unity.actions..ctor.md)||

## Methods

|Name|Description|
|:---|:---|
|[AddCommandHandler(string,Action)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-14.md)||
|[AddCommandHandler(string,Delegate)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-1.md)||
|[AddCommandHandler(string,Func<IEnumerator>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-25.md)||
|[AddCommandHandler(string,Func<Coroutine>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-3.md)||
|[AddCommandHandler(string,MethodInfo)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-2.md)||
|[AddCommandHandler(string,Action<T1>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-15.md)||
|[AddCommandHandler(string,Func<T1, IEnumerator>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-26.md)||
|[AddCommandHandler(string,Func<T1, Coroutine>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-4.md)||
|[AddCommandHandler(string,Action<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-24.md)||
|[AddCommandHandler(string,Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, IEnumerator>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-35.md)||
|[AddCommandHandler(string,Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, Coroutine>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-13.md)||
|[AddCommandHandler(string,Action<T1, T2>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-16.md)||
|[AddCommandHandler(string,Func<T1, T2, IEnumerator>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-27.md)||
|[AddCommandHandler(string,Func<T1, T2, Coroutine>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-5.md)||
|[AddCommandHandler(string,Action<T1, T2, T3>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-17.md)||
|[AddCommandHandler(string,Func<T1, T2, T3, IEnumerator>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-28.md)||
|[AddCommandHandler(string,Func<T1, T2, T3, Coroutine>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-6.md)||
|[AddCommandHandler(string,Action<T1, T2, T3, T4>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-18.md)||
|[AddCommandHandler(string,Func<T1, T2, T3, T4, IEnumerator>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-29.md)||
|[AddCommandHandler(string,Func<T1, T2, T3, T4, Coroutine>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-7.md)||
|[AddCommandHandler(string,Action<T1, T2, T3, T4, T5>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-19.md)||
|[AddCommandHandler(string,Func<T1, T2, T3, T4, T5, IEnumerator>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-30.md)||
|[AddCommandHandler(string,Func<T1, T2, T3, T4, T5, Coroutine>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-8.md)||
|[AddCommandHandler(string,Action<T1, T2, T3, T4, T5, T6>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-20.md)||
|[AddCommandHandler(string,Func<T1, T2, T3, T4, T5, T6, IEnumerator>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-31.md)||
|[AddCommandHandler(string,Func<T1, T2, T3, T4, T5, T6, Coroutine>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-9.md)||
|[AddCommandHandler(string,Action<T1, T2, T3, T4, T5, T6, T7>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-21.md)||
|[AddCommandHandler(string,Func<T1, T2, T3, T4, T5, T6, T7, IEnumerator>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-32.md)||
|[AddCommandHandler(string,Func<T1, T2, T3, T4, T5, T6, T7, Coroutine>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-10.md)||
|[AddCommandHandler(string,Action<T1, T2, T3, T4, T5, T6, T7, T8>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-22.md)||
|[AddCommandHandler(string,Func<T1, T2, T3, T4, T5, T6, T7, T8, IEnumerator>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-33.md)||
|[AddCommandHandler(string,Func<T1, T2, T3, T4, T5, T6, T7, T8, Coroutine>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-11.md)||
|[AddCommandHandler(string,Action<T1, T2, T3, T4, T5, T6, T7, T8, T9>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-23.md)||
|[AddCommandHandler(string,Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, IEnumerator>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-34.md)||
|[AddCommandHandler(string,Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, Coroutine>)](/docs/api/csharp/yarn.unity.actions.addcommandhandler-12.md)||
|[AddFunction(string,Delegate)](/docs/api/csharp/yarn.unity.actions.addfunction-1.md)||
|[AddFunction(string,Func<TResult>)](/docs/api/csharp/yarn.unity.actions.addfunction-2.md)||
|[AddFunction(string,Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, TResult>)](/docs/api/csharp/yarn.unity.actions.addfunction-11.md)||
|[AddFunction(string,Func<T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, TResult>)](/docs/api/csharp/yarn.unity.actions.addfunction-12.md)||
|[AddFunction(string,Func<T1, TResult>)](/docs/api/csharp/yarn.unity.actions.addfunction-3.md)||
|[AddFunction(string,Func<T1, T2, TResult>)](/docs/api/csharp/yarn.unity.actions.addfunction-4.md)||
|[AddFunction(string,Func<T1, T2, T3, TResult>)](/docs/api/csharp/yarn.unity.actions.addfunction-5.md)||
|[AddFunction(string,Func<T1, T2, T3, T4, TResult>)](/docs/api/csharp/yarn.unity.actions.addfunction-6.md)||
|[AddFunction(string,Func<T1, T2, T3, T4, T5, TResult>)](/docs/api/csharp/yarn.unity.actions.addfunction-7.md)||
|[AddFunction(string,Func<T1, T2, T3, T4, T5, T6, TResult>)](/docs/api/csharp/yarn.unity.actions.addfunction-8.md)||
|[AddFunction(string,Func<T1, T2, T3, T4, T5, T6, T7, TResult>)](/docs/api/csharp/yarn.unity.actions.addfunction-9.md)||
|[AddFunction(string,Func<T1, T2, T3, T4, T5, T6, T7, T8, TResult>)](/docs/api/csharp/yarn.unity.actions.addfunction-10.md)||
|[AddRegistrationMethod(Action<IActionRegistration>)](/docs/api/csharp/yarn.unity.actions.addregistrationmethod.md)||
|[GetLibrary()](/docs/api/csharp/yarn.unity.actions.getlibrary.md)||
|[RegisterActions()](/docs/api/csharp/yarn.unity.actions.registeractions.md)||
|[RemoveCommandHandler(string)](/docs/api/csharp/yarn.unity.actions.removecommandhandler.md)||
|[RemoveFunction(string)](/docs/api/csharp/yarn.unity.actions.removefunction.md)||
|[SetupForProject(YarnProject)](/docs/api/csharp/yarn.unity.actions.setupforproject.md)||

## Properties

|Name|Description|
|:---|:---|
|[Commands](/docs/api/csharp/yarn.unity.actions.commands.md)||
|[DialogueRunner](/docs/api/csharp/yarn.unity.actions.dialoguerunner.md)||
|[Library](/docs/api/csharp/yarn.unity.actions.library.md)||

