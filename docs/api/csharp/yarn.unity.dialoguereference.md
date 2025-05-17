# DialogueReference

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from `System.Object`

## Summary


Stores a reference to a dialogue node in a Yarn Project.


```csharp
public sealed class DialogueReference
```

## Remarks


A Dialogue Reference is a reference to a named node inside a given Yarn
Project. This allows the editor to warn the user if node doesn't exist
in the specified project.


## Constructors

|Name|Description|
|:---|:---|
|[DialogueReference()](/docs/api/csharp/yarn.unity.dialoguereference..ctor-1.md)|Creates an empty dialogue reference.|
|[DialogueReference(YarnProject,string)](/docs/api/csharp/yarn.unity.dialoguereference..ctor-2.md)|Creates a dialogue reference with a given project and node name.|

## Fields

|Name|Description|
|:---|:---|
|[nodeName](/docs/api/csharp/yarn.unity.dialoguereference.nodename.md)|The name of the dialogue node in the project.|
|[project](/docs/api/csharp/yarn.unity.dialoguereference.project.md)|The Yarn Project asset containing the dialogue node.|

## Properties

|Name|Description|
|:---|:---|
|[IsValid](/docs/api/csharp/yarn.unity.dialoguereference.isvalid.md)|Gets a value indicating that this reference is valid - that is, the project and node name are set, and the node exists in the project.|

