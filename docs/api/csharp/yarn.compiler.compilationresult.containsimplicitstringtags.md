# ContainsImplicitStringTags

Property in [CompilationResult](yarn.compiler.compilationresult.md)

## Summary

Gets a value indicating whether the compiler had to create line IDs for lines in the source code that lacked `#line:` tags.

```csharp
public bool ContainsImplicitStringTags { get; internal set; }
```

## Remarks

Every line is required to have a line ID. If a line doesn't have a line ID specified in the source code (via a `#line:` tag), the compiler will create one.

Implicit line IDs are guaranteed to remain the same between compilations when the source file does not change. If you want line IDs to remain the same when the source code may be modified in the future, add a `#line:` tag to the line. This may be done by hand, or added using the [AddTagsToLines(string,ICollection\<string>)](yarn.compiler.utility.addtagstolines.md) method.
