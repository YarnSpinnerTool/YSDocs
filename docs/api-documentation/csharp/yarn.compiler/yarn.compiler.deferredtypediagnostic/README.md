# DeferredTypeDiagnostic

Class in [Yarn.Compiler](../)

Inherits from `System.Object`

## Summary

Represents a potential type error diagnostic message.

```csharp
public class DeferredTypeDiagnostic
```

## Remarks

Because a variable can be declared in a scope different from the current yarn file, or even externally, when we first hit upon any variables of which we don't know the type of we create a deferred diagnostic. The idea being that we are hoping another file or step will give the information needed to resolved the type. Later once the compiler has finished parsing every file we can see if any of these weren't resolved. If they were not they will be promoted into a full diagnostic and presented to the user.

## Methods

| Name                                                                                                                    | Description                                                       |
| ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| [CreateDeferredTypeDiagnostic(string,Diagnostic)](yarn.compiler.deferredtypediagnostic.createdeferredtypediagnostic.md) | Convenience method for constructing new deferred type diagnostics |

## Properties

| Name                                                             | Description                                                            |
| ---------------------------------------------------------------- | ---------------------------------------------------------------------- |
| [diagnostic](yarn.compiler.deferredtypediagnostic.diagnostic.md) | The [Diagnostic](../yarn.compiler.diagnostic/) that has been deferred. |
| [Name](yarn.compiler.deferredtypediagnostic.name.md)             | The name of the variable who's type error is being deferred            |
