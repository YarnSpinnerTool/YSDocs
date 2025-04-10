# continueButton

Field in [LineView](yarn.unity.lineview.md)

## Summary

The game object that represents an on-screen button that the user can click to continue to the next piece of dialogue.

```csharp
public GameObject continueButton = null;
```

## Remarks

This game object will be made inactive when a line begins appearing, and active when the line has finished appearing.

This field will generally refer to an object that has a `UnityEngine.UI.Button` component on it that, when clicked, calls [OnContinueClicked()](yarn.unity.lineview.oncontinueclicked.md). However, if your game requires specific UI needs, you can provide any object you need.

## See Also

* [LineView.autoAdvance](yarn.unity.lineview.autoadvance.md): Controls whether this Line View will wait for user input before indicating that it has finished presenting a line.
