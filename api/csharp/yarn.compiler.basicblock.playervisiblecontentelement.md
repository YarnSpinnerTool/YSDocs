# PlayerVisibleContentElement

Class in [BasicBlock](api/csharp/yarn.compiler.basicblock.md)

Inherits from `System.Object`

## Summary


An abstract class that represents some content that is shown to the
player.


```csharp
public abstract class PlayerVisibleContentElement
```

## Remarks


This class is used, rather than the runtime classes Yarn.Line or
Yarn.OptionSet, because when the program is being analysed, no
values for any substitutions are available. Instead, these classes
represent the data that is available offline.


