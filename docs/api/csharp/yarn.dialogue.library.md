# Dialogue.Library

Property in [Dialogue](/docs/api/csharp/yarn.dialogue.md)

## Summary


Gets the  <a href="yarn.library.md">Library</a>  that this Dialogue uses to
locate functions.


```csharp
public Library Library { get; internal set; }
```

## Remarks


When the Dialogue is constructed, the Library is initialized with
the built-in operators like  `+` ,  `-` , and so on.


