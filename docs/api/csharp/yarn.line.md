# Line

Struct in [Yarn](yarn.md)

Inherits from `System.ValueType`

## Summary

A line of dialogue, sent from the [Dialogue](yarn.dialogue.md) to the game.

```csharp
public struct Line
```

## Remarks

When the game receives a [Line](yarn.line.md), it should do the\
following things to prepare the line for presentation to the user.

1. Use the value in the [ID](yarn.line.id.md) field to look up the\
   appropriate user-facing text in the string table.
2. Use [ExpandSubstitutions(string,IList\<string>)](yarn.markup.lineparser.expandsubstitutions.md) to replace all\
   substitutions in the user-facing text.
3. Use `Yarn.Markup.LineParser.ParseString(System.String,System.String,System.Boolean,System.Boolean,System.Boolean)` to parse all markup in the\
   line.

You typically do not create instances of this struct yourself.\
They are created by the [Dialogue](yarn.dialogue.md) during program\
execution.

## Constructors

| Name                                          | Description                                                    |
| --------------------------------------------- | -------------------------------------------------------------- |
| [Line(string,string\[\])](yarn.line..ctor.md) | Initialises a new instance of the [Line](yarn.line.md) struct. |

## Properties

| Name                                        | Description                                                                   |
| ------------------------------------------- | ----------------------------------------------------------------------------- |
| [ID](yarn.line.id.md)                       | The string ID for this line.                                                  |
| [Substitutions](yarn.line.substitutions.md) | The values that should be inserted into the user-facing text before delivery. |

## See Also

* [Dialogue.LineHandler](yarn.dialogue.linehandler.md): Gets or sets the [LineHandler](yarn.linehandler.md) that is called when a line is ready to be shown to the user.
