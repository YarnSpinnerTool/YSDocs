# Project.LoadFromFile(string,string?)

Method in [Project](/docs/api/csharp/yarn.compiler.project.md)

## Summary


Loads and parses a  <a href="yarn.compiler.project.md">Project</a>  from a file on disk.


```csharp
public static Project LoadFromFile(string path, string? workspaceRoot = null)
```

## Parameters

|Name|Description|
|:---|:---|
|`string` path|The path to the file to load.|
|`string` workspaceRoot|The path of the root of the workspace in which  `file`  is located.|

## Returns

The loaded  <a href="yarn.compiler.project.md">Project</a> .

