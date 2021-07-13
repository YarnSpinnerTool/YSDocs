# OptionSet Struct

A set of [`OptionSet.Option`](/api/csharp/yarn/optionset.option.md)s, sent from the [`Dialogue`](/api/csharp/yarn/dialogue.md) to the game.


```csharp
public struct OptionSet
```
## Remarks

You do not create instances of this struct yourself. They are
created by the [`Dialogue`](/api/csharp/yarn/dialogue.md) during program execution.




## Properties
|Name|Description|
|:---|:---|
|[`Options`](/api/csharp/yarn/optionset.options.md)| Gets the [`OptionSet.Option`](/api/csharp/yarn/optionset.option.md)s that should be presented to the user. |
## See Also
* [`OptionsHandler`](/api/csharp/yarn/dialogue.optionshandler.md): 
Gets or sets the [`OptionsHandler`](/api/csharp/yarn/optionshandler.md) that is
called when a set of options are ready to be shown to the user.

<div class="class-metadata">

Namespace: [`Yarn`](/api/csharp/yarn/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L85), line 85.
