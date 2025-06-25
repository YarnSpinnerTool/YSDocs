# IActionRegistration

Interface in [Yarn.Unity](yarn.unity.md)

## Summary

Contains methods that allow adding and removing Yarn commands and\
functions.

```csharp
public interface IActionRegistration
```

## Methods

| Name                                                                                                               | Description                                                                          |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| [AddCommandHandler(string,Delegate)](yarn.unity.iactionregistration.addcommandhandler-1.md)                        | Adds a command handler. Dialogue will pause execution after the command is called.   |
| [AddCommandHandler(string,MethodInfo)](yarn.unity.iactionregistration.addcommandhandler-2.md)                      | Adds a command handler. Dialogue will pause execution after the command is called.   |
| [AddFunction(string,Delegate)](yarn.unity.iactionregistration.addfunction.md)                                      | Add a new function that returns a value, so that it can be called from Yarn scripts. |
| [RegisterFunctionDeclaration(string,Type,Type\[\])](yarn.unity.iactionregistration.registerfunctiondeclaration.md) | Registers a function as existing, without supplying an implementation.               |
| [RemoveCommandHandler(string)](yarn.unity.iactionregistration.removecommandhandler.md)                             | Removes a command handler.                                                           |
| [RemoveFunction(string)](yarn.unity.iactionregistration.removefunction.md)                                         | Remove a registered function.                                                        |
