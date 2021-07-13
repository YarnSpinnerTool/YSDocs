# Dialogue.ExpandSubstitutions Method

Replaces all substitution markers in a text with the given
substitution list.


```csharp
public static string ExpandSubstitutions(string text, IList<string> substitutions)
```
## Remarks

This method replaces substitution markers - for example, `{0}`
- with the corresponding entry in <code data-dev-comment-type="paramref" class="paramref">substitutions</code>. If <code data-dev-comment-type="paramref" class="paramref">text</code> contains a
substitution marker whose index is not present in <code data-dev-comment-type="paramref" class="paramref">substitutions</code>, it is ignored.


## Parameters
|Parameter|Description|
|:---|:---|
|[`string`](https://docs.microsoft.com/dotnet/api/System.String) text|The text containing substitution markers.|
|[`String}`](https://docs.microsoft.com/dotnet/api/System.Collections.Generic.IList{System.String}) substitutions|The list of substitutions.|
## Return Type
[`string`](https://docs.microsoft.com/dotnet/api/System.String): <code data-dev-comment-type="paramref" class="paramref">text</code>, with the content from
<code data-dev-comment-type="paramref" class="paramref">substitutions</code> inserted.



<div class="class-metadata">

Parent: [`Dialogue`](/api/csharp/yarn/dialogue.md), Namespace: [`Yarn`](/api/csharp/yarn/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L896), line 896.
