# OptionSet

Struct in [Yarn](/api/csharp/yarn.md)

Inherits from `System.ValueType`

## Summary


A set of  <a href="yarn.optionset.option.md">Option</a> s, sent from the  <a href="yarn.dialogue.md">Dialogue</a>  to the game.


```csharp
public struct OptionSet
```

## Remarks


You do not create instances of this struct yourself. They are
created by the  <a href="yarn.dialogue.md">Dialogue</a>  during program execution.


## Properties

|Name|Description|
|:---|:---|
|[Options](/api/csharp/yarn.optionset.options.md)|Gets the  <a href="yarn.optionset.option.md">Option</a> s that should be presented to the user.|

## Structs

|Name|Description|
|:---|:---|
|[Option](/api/csharp/yarn.optionset.option.md)|An option to be presented to the user.|

## See Also

* [Dialogue.OptionsHandler](/api/csharp/yarn.dialogue.optionshandler.md): Gets or sets the  <a href="yarn.optionshandler.md">OptionsHandler</a>  that is called when a set of options are ready to be shown to the user.

