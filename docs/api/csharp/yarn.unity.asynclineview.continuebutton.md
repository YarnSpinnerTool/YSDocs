# continueButton

Field in [AsyncLineView](yarn.unity.asynclineview.md)

## Summary

The `UnityEngine.UI.Button` that represents an on-screen button that the user can click to continue to the next piece of dialogue.

```csharp
public Button? continueButton;
```

## Remarks

This button's game object will be made inactive when a line begins appearing, and active when the line has finished appearing.

When the button is clicked, `Yarn.Unity.AsyncLineView.dialogueRunner`'s [RequestNextLine()](yarn.unity.dialoguerunner.requestnextline.md) will be called to signal that the current line should finish up.

## See Also

* [AsyncLineView.autoAdvance](yarn.unity.asynclineview.autoadvance.md): Controls whether this Line View will automatically to the Dialogue Runner that the line is complete as soon as the line has finished appearing.
