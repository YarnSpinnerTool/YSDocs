# Line

Struct in [Yarn](/docs/api/csharp/yarn.md)

Inherits from `System.ValueType`

## Summary


A line of dialogue, sent from the  <a href="yarn.dialogue.md">Dialogue</a>  to the game.


```csharp
public struct Line
```

## Remarks

<p>When the game receives a <a href="yarn.line.md">Line</a>, it should do the
following things to prepare the line for presentation to the user.
</p> <ol type="number">
<li>Use the value in the <a href="yarn.line.id.md">ID</a> field to look up the
appropriate user-facing text in the string table. </li>
<li>Use <a href="yarn.markup.lineparser.expandsubstitutions.md">ExpandSubstitutions(string,IList&lt;string&gt;)</a> to replace all
substitutions in the user-facing text.</li>
<li>Use <code>Yarn.Markup.LineParser.ParseString(System.String,System.String,System.Boolean,System.Boolean,System.Boolean)</code> to parse all markup in the
line.</li>
</ol> <p>You typically do not create instances of this struct yourself.
They are created by the <a href="yarn.dialogue.md">Dialogue</a> during program
execution.</p>

## Constructors

|Name|Description|
|:---|:---|
|[Line(string,string[])](/docs/api/csharp/yarn.line..ctor.md)|Initialises a new instance of the  <a href="yarn.line.md">Line</a>  struct.|

## Properties

|Name|Description|
|:---|:---|
|[ID](/docs/api/csharp/yarn.line.id.md)|The string ID for this line.|
|[Substitutions](/docs/api/csharp/yarn.line.substitutions.md)|The values that should be inserted into the user-facing text before delivery.|

## See Also

* [Dialogue.LineHandler](/docs/api/csharp/yarn.dialogue.linehandler.md): Gets or sets the  <a href="yarn.linehandler.md">LineHandler</a>  that is called when a line is ready to be shown to the user.

