# LineView.continueButton

Field in [LineView](/docs/api/csharp/yarn.unity.legacy.lineview.md)

## Summary


The game object that represents an on-screen button that the user
can click to continue to the next piece of dialogue.


```csharp
public GameObject? continueButton = null;
```

## Remarks

<p>This game object will be made inactive when a line begins
appearing, and active when the line has finished appearing.</p> <p>
This field will generally refer to an object that has a `UnityEngine.UI.Button` component on it that, when clicked, calls <a href="yarn.unity.legacy.lineview.oncontinueclicked.md">OnContinueClicked()</a>. However, if your game requires specific
UI needs, you can provide any object you need.</p>

## See Also

* [LineView.autoAdvance](/docs/api/csharp/yarn.unity.legacy.lineview.autoadvance.md): Controls whether this Line View will wait for user input before indicating that it has finished presenting a line.

