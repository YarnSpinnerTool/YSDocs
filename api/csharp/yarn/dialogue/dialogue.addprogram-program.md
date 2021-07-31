# AddProgram\(Program\)

Loads the nodes from the specified [`Program`](../program/), and adds them to the nodes already loaded.

```csharp
public void AddProgram(Program program)
```

## Remarks

If `Yarn.Dialogue.Program` is `null`, this method has the effect as calling [`SetProgram(Program)`](dialogue.setprogram-program.md).

## Parameters

| Parameter | Description |
| :--- | :--- |
| [`Program`](../program/) program | The additional program to load. |

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/Dialogue.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/Dialogue.cs#L582), line 582.

