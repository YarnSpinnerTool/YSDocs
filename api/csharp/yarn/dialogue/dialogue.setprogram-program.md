# SetProgram\(Program\)

Loads all nodes from the provided [`Program`](../program/).

```csharp
public void SetProgram(Program program)
```

## Remarks

This method replaces any existing nodes have been loaded. If you want to load nodes from an _additional_ Program, use the [`AddProgram(Program)`](dialogue.addprogram-program.md) method.

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`Program`](../program/) program | The [`Program`](../program/) to use. |

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L568), line 568.

