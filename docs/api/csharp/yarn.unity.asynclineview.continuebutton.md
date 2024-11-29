# AsyncLineView.continueButton

Field in [AsyncLineView](/docs/api/csharp/yarn.unity.asynclineview.md)

## Summary


The  <code>UnityEngine.UI.Button</code>  that represents an on-screen button that
the user can click to continue to the next piece of dialogue.


```csharp
public Button? continueButton;
```

## Remarks

<p>This button's game object will be made inactive when a line
begins appearing, and active when the line has finished
appearing.</p> <p>When the button is clicked, <code>Yarn.Unity.AsyncLineView.dialogueRunner</code>'s
<a href="yarn.unity.dialoguerunner.requestnextline.md">RequestNextLine()</a> will be called to
signal that the current line should finish up.</p>

## See Also

* [AsyncLineView.autoAdvance](/docs/api/csharp/yarn.unity.asynclineview.autoadvance.md): Controls whether this Line View will automatically to the Dialogue Runner that the line is complete as soon as the line has finished appearing.

