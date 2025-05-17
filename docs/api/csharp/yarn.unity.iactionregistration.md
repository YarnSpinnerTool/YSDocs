# IActionRegistration

Interface in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

## Summary


Contains methods that allow adding and removing Yarn commands and
functions.


```csharp
public interface IActionRegistration
```

## Methods

|Name|Description|
|:---|:---|
|[AddCommandHandler(string,Delegate)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-1.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddCommandHandler(string,MethodInfo)](/docs/api/csharp/yarn.unity.iactionregistration.addcommandhandler-2.md)|Adds a command handler. Dialogue will pause execution after the command is called.|
|[AddFunction(string,Delegate)](/docs/api/csharp/yarn.unity.iactionregistration.addfunction.md)|Add a new function that returns a value, so that it can be called from Yarn scripts.|
|[RegisterFunctionDeclaration(string,Type,Type[])](/docs/api/csharp/yarn.unity.iactionregistration.registerfunctiondeclaration.md)|Registers a function as existing, without supplying an implementation.|
|[RemoveCommandHandler(string)](/docs/api/csharp/yarn.unity.iactionregistration.removecommandhandler.md)|Removes a command handler.|
|[RemoveFunction(string)](/docs/api/csharp/yarn.unity.iactionregistration.removefunction.md)|Remove a registered function.|

