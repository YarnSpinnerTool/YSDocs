# useFadeEffect

Field in [LineView](yarn.unity.legacy.lineview.md)

## Summary

Controls whether the line view should fade in when lines appear, and\
fade out when lines disappear.

```csharp
public bool useFadeEffect = true;
```

## Remarks

If this value is `true`, the [canvasGroup](yarn.unity.legacy.lineview.canvasgroup.md) object's alpha property will animate from 0 to\
1 over the course of [fadeInTime](yarn.unity.legacy.lineview.fadeintime.md) seconds when lines\
appear, and animate from 1 to zero over the course of [fadeOutTime](yarn.unity.legacy.lineview.fadeouttime.md) seconds when lines disappear.

If this value is `false`, the [canvasGroup](yarn.unity.legacy.lineview.canvasgroup.md) object will appear instantaneously.

## See Also

* [LineView.canvasGroup](yarn.unity.legacy.lineview.canvasgroup.md): The canvas group that contains the UI elements used by this Line View.
* [LineView.fadeInTime](yarn.unity.legacy.lineview.fadeintime.md): The time that the fade effect will take to fade lines in.
* [LineView.fadeOutTime](yarn.unity.legacy.lineview.fadeouttime.md): The time that the fade effect will take to fade lines out.
