# Line

Struct in [Yarn](/api/csharp/yarn.md)

Inherits from `System.ValueType`

## Summary


A line of dialogue, sent from the  <a href="yarn.dialogue.md">Dialogue</a>  to the
game.


```csharp
public struct Line
```

## Remarks


When the game receives a  <a href="yarn.line.md">Line</a> , it should do the
following things to prepare the line for presentation to the user. 

1. Use the value in the  <a href="yarn.line.id.md">ID</a>  field to look up the
appropriate user-facing text in the string table. 

2. Use  <a href="yarn.dialogue.expandsubstitutions.md">ExpandSubstitutions(string,IList&lt;string&gt;)</a>  to replace all
substitutions in the user-facing text.

3. Use  <a href="yarn.dialogue.parsemarkup.md">ParseMarkup(string)</a>  to parse all markup in
the line.

You do not create instances of this struct yourself. They are
created by the  <a href="yarn.dialogue.md">Dialogue</a>  during program execution.


## Fields

|Name|Description|
|:---|:---|
|[ID](/api/csharp/yarn.line.id.md)|The string ID for this line.|
|[Substitutions](/api/csharp/yarn.line.substitutions.md)|The values that should be inserted into the user-facing text before delivery.|

## See Also

* [Dialogue.LineHandler](/api/csharp/yarn.dialogue.linehandler.md): Gets or sets the  <a href="yarn.linehandler.md">LineHandler</a>  that is called when a line is ready to be shown to the user.

