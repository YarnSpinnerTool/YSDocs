# LineView.useFadeEffect

Field in [LineView](/docs/api/csharp/yarn.unity.legacy.lineview.md)

## Summary


Controls whether the line view should fade in when lines appear, and
fade out when lines disappear.


```csharp
public bool useFadeEffect = true;
```

## Remarks

<p>If this value is `true`, the <a href="yarn.unity.legacy.lineview.canvasgroup.md">canvasGroup</a> object's alpha property will animate from 0 to
1 over the course of <a href="yarn.unity.legacy.lineview.fadeintime.md">fadeInTime</a> seconds when lines
appear, and animate from 1 to zero over the course of <a href="yarn.unity.legacy.lineview.fadeouttime.md">fadeOutTime</a> seconds when lines disappear.</p> <p>If this value is `false`, the <a href="yarn.unity.legacy.lineview.canvasgroup.md">canvasGroup</a> object will appear instantaneously.</p>

## See Also

* [LineView.canvasGroup](/docs/api/csharp/yarn.unity.legacy.lineview.canvasgroup.md): The canvas group that contains the UI elements used by this Line View.
* [LineView.fadeInTime](/docs/api/csharp/yarn.unity.legacy.lineview.fadeintime.md): The time that the fade effect will take to fade lines in.
* [LineView.fadeOutTime](/docs/api/csharp/yarn.unity.legacy.lineview.fadeouttime.md): The time that the fade effect will take to fade lines out.

