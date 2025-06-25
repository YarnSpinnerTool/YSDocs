# useTypewriterEffect

Field in [LinePresenter](yarn.unity.linepresenter.md)

## Summary

Controls whether the text of [lineText](yarn.unity.linepresenter.linetext.md) should be\
gradually revealed over time.

```csharp
public bool useTypewriterEffect = true;
```

## Remarks

If this value is `true`, the [lineText](yarn.unity.linepresenter.linetext.md) object's `TMPro.TMP_Text.maxVisibleCharacters` property will animate from 0\
to the length of the text, at a rate of [typewriterEffectSpeed](yarn.unity.linepresenter.typewritereffectspeed.md) letters per second when the line\
appears. `onCharacterTyped` is called for every new\
character that is revealed.

If this value is `false`, the [lineText](yarn.unity.linepresenter.linetext.md) will all be revealed at the same time.

{% hint style="info" %}
If [useFadeEffect](yarn.unity.linepresenter.usefadeeffect.md) is `true`, the typewriter effect will run after the fade-in\
is complete.
{% endhint %}

## See Also

* [LinePresenter.lineText](yarn.unity.linepresenter.linetext.md): The `TMPro.TMP_Text` object that displays the text of dialogue lines.
* onCharacterTyped
* [LinePresenter.typewriterEffectSpeed](yarn.unity.linepresenter.typewritereffectspeed.md): The number of characters per second that should appear during a typewriter effect.
