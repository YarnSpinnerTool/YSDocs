# ReplacementMarkerResult.InvisibleCharacters

Field in [ReplacementMarkerResult](/docs/api/csharp/yarn.markup.replacementmarkerresult.md)

## Summary


The number of invisible characters added into the line during processing.


```csharp
public int InvisibleCharacters;
```

## Remarks


This will vary depending on what the replacement markup needs to do.
<ul type="bullet">
<li>
<p>
When only inserting rich-text tags, this should be the length of all inserted text.
For example <code>"this is text with [bold]some bold[/bold] elements"</code> translated into Unity style rich-text become <code>"this is text with &lt;b&gt;some bold&lt;/b&gt; elements"</code>.
In this case then the value of <code>InvisibleCharacters</code> would be seven.
</p>
</li>
<li>
<p>
When only modifying the content of the children text, such as making all text upper case, this should be <code>0</code>.
For example <code>"this is text with [upper]some uppercased[/upper] elements"</code> is transformed into <code>"this is text with SOME UPPERCASED elements"</code>.
The number of invisible character will be zero.
</p>
</li>
<li>
When adding new content into the line (regardless of being added at the start, end, or middle) this should be zero but the replacement processor should make sure to shift along it's children attributes where appropriate.
For example <code>"this is text with [emph]some emphasised[/emph] elements"</code> transformed into <code>"this is text with !!some emphasised!! elements"</code> the value of <code>InvisibleCharacters</code> would be zero.
In this case however the <code>childAttributes</code> in <a href="yarn.markup.iattributemarkerprocessor.processreplacementmarker.md">ProcessReplacementMarker(MarkupAttribute,System.Text.StringBuilder,List&lt;MarkupAttribute&gt;,string)</a> would need to be shifted down two.
</li>
</ul>

