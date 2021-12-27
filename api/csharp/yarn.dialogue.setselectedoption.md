# Dialogue.SetSelectedOption(int)

Method in [Dialogue](/api/csharp/yarn.dialogue.md)

## Summary


Signals to the  <a href="yarn.dialogue.md">Dialogue</a>  that the user has
selected a specified  <a href="yarn.optionset.option.md">Option</a> .


```csharp
public void SetSelectedOption(int selectedOptionID)
```

## Remarks


After the Dialogue delivers an  <a href="yarn.optionset.md">OptionSet</a> , this
method must be called before  <a href="yarn.dialogue.continue.md">Continue()</a>  is called.

The ID number that should be passed as the parameter to this
method should be the  <a href="yarn.optionset.option.id.md">ID</a>  field in
the  <a href="yarn.optionset.option.md">Option</a>  that represents the user's
selection.


## Parameters

|Name|Description|
|:---|:---|
|selectedOptionID|The ID number of the Option that the user selected.|

## Returns



## See Also

* [OptionsHandler](/api/csharp/yarn.optionshandler.md): Represents the method that is called when the Dialogue delivers an <a href="yarn.optionset.md">OptionSet</a> .
* [OptionSet](/api/csharp/yarn.optionset.md): A set of  <a href="yarn.optionset.option.md">Option</a> s, sent from the  <a href="yarn.dialogue.md">Dialogue</a>  to the game.
* [Continue\()](/api/csharp/yarn.dialogue.continue.md): Starts, or continues, execution of the current Program.

