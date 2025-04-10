# useFadeEffect

Field in [AsyncLineView](yarn.unity.asynclineview.md)

## Summary

Controls whether the line view should fade in when lines appear, and fade out when lines disappear.

```csharp
public bool useFadeEffect = true;
```

## Remarks

If this value is `true`, the [canvasGroup](yarn.unity.asynclineview.canvasgroup.md) object's alpha property will animate from 0 to 1 over the course of [fadeUpDuration](yarn.unity.asynclineview.fadeupduration.md) seconds when lines appear, and animate from 1 to zero over the course of [fadeDownDuration](yarn.unity.asynclineview.fadedownduration.md) seconds when lines disappear.

If this value is `false`, the [canvasGroup](yarn.unity.asynclineview.canvasgroup.md) object will appear instantaneously.

## See Also

* [AsyncLineView.canvasGroup](yarn.unity.asynclineview.canvasgroup.md): The canvas group that contains the UI elements used by this Line View.
* [AsyncLineView.fadeUpDuration](yarn.unity.asynclineview.fadeupduration.md): The time that the fade effect will take to fade lines in.
* [AsyncLineView.fadeDownDuration](yarn.unity.asynclineview.fadedownduration.md): The time that the fade effect will take to fade lines out.
