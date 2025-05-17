# Utility.GenerateYarnFileWithDeclarations(IEnumerable<Yarn.Compiler.Declaration>,string,IEnumerable<string>?,IDictionary<string, string>?)

Method in [Utility](/docs/api/csharp/yarn.compiler.utility.md)

## Summary


Generates a Yarn script that contains a node that declares
variables.


```csharp
public static string GenerateYarnFileWithDeclarations(IEnumerable<Yarn.Compiler.Declaration> declarations, string title = "Program", IEnumerable<string>? tags = null, IDictionary<string, string>? headers = null)
```

## Remarks

This method is intended to be called by tools that let the
user manage variable declarations. Such tools can read the existing
variable declarations in from a script (by compiling the script with
the  <a href="yarn.compiler.compilationjob.compilationtype.md">CompilationType</a>  value set to   <a href="yarn.compiler.compilationjob.type.typecheck.md">TypeCheck</a> ), allow the user to
make changes, and then write the changes to disk by calling this
method and saving the results.

## Parameters

|Name|Description|
|:---|:---|
|`System.Collections.Generic.IEnumerable<Yarn.Compiler.Declaration>` declarations|The collection of  <a href="yarn.compiler.declaration.md">Declaration</a>  objects to include in the output.|
|`string` title|The title of the node that should be generated.|
|`System.Collections.Generic.IEnumerable<string>` tags|The collection of tags that should be generated for the node. If this is  `null` , no tags will be generated.|
|`System.Collections.Generic.IDictionary<string, string>` headers|The collection of additional headers that should be generated for the node. If this is  `null` , no additional headers will be generated.|

## Returns

A string containing a Yarn script that declares the
specified variables.

