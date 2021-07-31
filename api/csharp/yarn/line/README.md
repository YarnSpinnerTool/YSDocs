# Line

A line of dialogue, sent from the [`Dialogue`](../dialogue/) to the game.

```csharp
public struct Line
```

## Remarks

When the game receives a [`Line`](./), it should do the following things to prepare the line for presentation to the user.

1. Use the value in the [`ID`](line.id.md) field to look up the appropriate user-facing text in the string table.
2. Use `Yarn.Dialogue.ExpandSubstitutions(System.String,System.Collections.Generic.IList%7bSystem.String%7d)` to replace all substitutions in the user-facing text.
3. Use [`ParseMarkup(String)`](../dialogue/dialogue.parsemarkup-system.string.md) to parse all markup in the line.

You do not create instances of this struct yourself. They are created by the [`Dialogue`](../dialogue/) during program execution.

## Fields

| Name | Description |
| :--- | :--- |
| [`ID`](line.id.md) | The string ID for this line. |
| [`Substitutions`](line.substitutions.md) | The values that should be inserted into the user-facing text before delivery. |

## See Also

* [`LineHandler`](../dialogue/dialogue.linehandler.md): 

  Gets or sets the [`LineHandler`](../linehandler.md) that is called

  when a line is ready to be shown to the user.

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L56), line 56.

