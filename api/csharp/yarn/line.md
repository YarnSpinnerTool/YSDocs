# Line Struct

A line of dialogue, sent from the [`Dialogue`](/api/csharp/yarn/dialogue.md) to the
game.


```csharp
public struct Line
```
## Remarks

When the game receives a [`Line`](/api/csharp/yarn/line.md), it should do the
following things to prepare the line for presentation to the user. 

1. Use the value in the [`ID`](/api/csharp/yarn/line.id.md) field to look up the
appropriate user-facing text in the string table. 

2. Use `Yarn.Dialogue.ExpandSubstitutions(System.String,System.Collections.Generic.IList%7bSystem.String%7d)` to replace all
substitutions in the user-facing text.

3. Use [`ParseMarkup(String)`](/api/csharp/yarn/dialogue.parsemarkup-system.string-.md) to parse all markup in
the line.

You do not create instances of this struct yourself. They are
created by the [`Dialogue`](/api/csharp/yarn/dialogue.md) during program execution.




## Fields
|Name|Description|
|:---|:---|
|[`ID`](/api/csharp/yarn/line.id.md)| The string ID for this line. |
|[`Substitutions`](/api/csharp/yarn/line.substitutions.md)| The values that should be inserted into the user-facing text before delivery. |
## See Also
* [`LineHandler`](/api/csharp/yarn/dialogue.linehandler.md): 
Gets or sets the [`LineHandler`](/api/csharp/yarn/linehandler.md) that is called
when a line is ready to be shown to the user.

## Namespace
[`Yarn`](/api/csharp/yarn/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L56), line 56.
