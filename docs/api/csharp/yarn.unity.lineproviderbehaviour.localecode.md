# LineProviderBehaviour.LocaleCode

Property in [LineProviderBehaviour](/api/csharp/yarn.unity.lineproviderbehaviour.md)

## Summary


Gets the user's current locale identifier, as a BCP-47 code.


```csharp
public abstract string LocaleCode { get; }
```

## Remarks


This value is used by the  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  to control
how certain replacement markers behave (for example, the
<code>[plural]</code>  marker, which behaves differently depending on the
user's locale.)


