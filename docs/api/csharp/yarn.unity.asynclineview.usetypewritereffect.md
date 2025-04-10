# useTypewriterEffect

Field in [AsyncLineView](yarn.unity.asynclineview.md)

## Summary

Controls whether the text of [lineText](yarn.unity.asynclineview.linetext.md) should be gradually revealed over time.

```csharp
public bool useTypewriterEffect = true;
```

## Remarks

If this value is `true`, the [lineText](yarn.unity.asynclineview.linetext.md) object's `TMPro.TMP_Text.maxVisibleCharacters` property will animate from 0 to the length of the text, at a rate of [typewriterEffectSpeed](yarn.unity.asynclineview.typewritereffectspeed.md) letters per second when the line appears. [onCharacterTyped](yarn.unity.asynclineview.oncharactertyped.md) is called for every new character that is revealed.

If this value is `false`, the [lineText](yarn.unity.asynclineview.linetext.md) will all be revealed at the same time.

{% hint style="info" %}
If [useFadeEffect](yarn.unity.asynclineview.usefadeeffect.md) is `true`, the typewriter effect will run after the fade-in is complete.
{% endhint %}

## See Also

* [AsyncLineView.lineText](yarn.unity.asynclineview.linetext.md): The `TMPro.TMP_Text` object that displays the text of dialogue lines.
* [AsyncLineView.onCharacterTyped](yarn.unity.asynclineview.oncharactertyped.md): A Unity Event that is called each time a character is revealed during a typewriter effect.
* [AsyncLineView.typewriterEffectSpeed](yarn.unity.asynclineview.typewritereffectspeed.md): The number of characters per second that should appear during a typewriter effect.
