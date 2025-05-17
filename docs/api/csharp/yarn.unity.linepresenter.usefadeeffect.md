# LinePresenter.useFadeEffect

Field in [LinePresenter](/docs/api/csharp/yarn.unity.linepresenter.md)

## Summary


Controls whether the line view should fade in when lines appear, and
fade out when lines disappear.


```csharp
public bool useFadeEffect = true;
```

## Remarks

<p>If this value is `true`, the [canvasGroup](yarn.unity.linepresenter.canvasgroup.md) object's alpha property will animate from 0 to
1 over the course of [fadeUpDuration](yarn.unity.linepresenter.fadeupduration.md) seconds when lines
appear, and animate from 1 to zero over the course of [canvasGroup](yarn.unity.linepresenter.fadedownduration.md">fadeDownDuration</a> seconds when lines disappear.</p> <p>If this value is `false`, the <a href="yarn.unity.linepresenter.canvasgroup.md) object will appear instantaneously.</p>

## See Also

* [LinePresenter.canvasGroup](/docs/api/csharp/yarn.unity.linepresenter.canvasgroup.md): The canvas group that contains the UI elements used by this Line View.
* [LinePresenter.fadeUpDuration](/docs/api/csharp/yarn.unity.linepresenter.fadeupduration.md): The time that the fade effect will take to fade lines in.
* [LinePresenter.fadeDownDuration](/docs/api/csharp/yarn.unity.linepresenter.fadedownduration.md): The time that the fade effect will take to fade lines out.

