# DialogueReference

Class in [Yarn.Unity](yarn.unity.md)

Inherits from `System.Object`

## Summary

Stores a reference to a dialogue node in a Yarn Project.

```csharp
public class DialogueReference
```

## Remarks

A Dialogue Reference is a reference to a named node inside a given Yarn Project. This allows the editor to warn the user if node doesn't exist in the specified project.

## Constructors

| Name                                                                             | Description                                                      |
| -------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| [DialogueReference()](yarn.unity.dialoguereference..ctor-1.md)                   | Creates an empty dialogue reference.                             |
| [DialogueReference(YarnProject,string)](yarn.unity.dialoguereference..ctor-2.md) | Creates a dialogue reference with a given project and node name. |

## Fields

| Name                                                 | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- |
| [nodeName](yarn.unity.dialoguereference.nodename.md) | The name of the dialogue node in the project.        |
| [project](yarn.unity.dialoguereference.project.md)   | The Yarn Project asset containing the dialogue node. |

## Properties

| Name                                               | Description                                                                                                                            |
| -------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| [IsValid](yarn.unity.dialoguereference.isvalid.md) | Gets a value indicating that this reference is valid - that is, the project and node name are set, and the node exists in the project. |

## TYPENAME\_UNKNOWN\_PLURAL

| Name                                                                                                                                    | Description |
| --------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| [M:Yarn.Unity.DialogueReference.op\_Implicit(Yarn.Unity.DialogueReference)\~System.String](yarn.unity.dialoguereference.op_implicit.md) |             |
