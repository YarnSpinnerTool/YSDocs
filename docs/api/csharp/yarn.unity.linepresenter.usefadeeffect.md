# useFadeEffect

Field in [LinePresenter](yarn.unity.linepresenter.md)

## Summary

Controls whether the line view should fade in when lines appear, and\
fade out when lines disappear.

```csharp
public bool useFadeEffect = true;
```

## Remarks

If this value is `true`, the [canvasGroup](yarn.unity.linepresenter.canvasgroup.md) object's alpha property will animate from 0 to\
1 over the course of [fadeUpDuration](yarn.unity.linepresenter.fadeupduration.md) seconds when lines\
appear, and animate from 1 to zero over the course of [fadeDownDuration](yarn.unity.linepresenter.fadedownduration.md) seconds when lines disappear.

If this value is `false`, the [canvasGroup](yarn.unity.linepresenter.canvasgroup.md) object will appear instantaneously.

## See Also

* [LinePresenter.canvasGroup](yarn.unity.linepresenter.canvasgroup.md): The canvas group that contains the UI elements used by this Line View.
* [LinePresenter.fadeUpDuration](yarn.unity.linepresenter.fadeupduration.md): The time that the fade effect will take to fade lines in.
* [LinePresenter.fadeDownDuration](yarn.unity.linepresenter.fadedownduration.md): The time that the fade effect will take to fade lines out.
