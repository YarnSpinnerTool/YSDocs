# Dialogue.AddProgram(Program)

Method in [Dialogue](/api/csharp/yarn.dialogue.md)

## Summary


Loads the nodes from the specified  <a href="yarn.program.md">Program</a> , and
adds them to the nodes already loaded.


```csharp
public void AddProgram(Program program)
```

## Remarks


If  <code>Yarn.Dialogue.Program</code>  is  <code>null</code> , this method has
the effect as calling  <a href="yarn.dialogue.setprogram.md">SetProgram(Program)</a> .


## Parameters

|Name|Description|
|:---|:---|
|[Yarn.Program](/api/csharp/yarn.program.md) program|The additional program to load.|

