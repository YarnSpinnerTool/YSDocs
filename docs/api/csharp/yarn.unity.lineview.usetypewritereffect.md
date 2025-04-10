# useTypewriterEffect

Field in [LineView](yarn.unity.lineview.md)

## Summary

Controls whether the text of [lineText](yarn.unity.lineview.linetext.md) should be gradually revealed over time.

```csharp
public bool useTypewriterEffect = false;
```

## Remarks

If this value is `true`, the [lineText](yarn.unity.lineview.linetext.md) object's `TMPro.TMP_Text.maxVisibleCharacters` property will animate from 0 to the length of the text, at a rate of [typewriterEffectSpeed](yarn.unity.lineview.typewritereffectspeed.md) letters per second when the line appears. [onCharacterTyped](yarn.unity.lineview.oncharactertyped.md) is called for every new character that is revealed.

If this value is `false`, the [lineText](yarn.unity.lineview.linetext.md) will all be revealed at the same time.

{% hint style="info" %}
If [useFadeEffect](yarn.unity.lineview.usefadeeffect.md) is `true`, the typewriter effect will run after the fade-in is complete.
{% endhint %}

## See Also

* [LineView.lineText](yarn.unity.lineview.linetext.md): The `TMPro.TextMeshProUGUI` object that displays the text of dialogue lines.
* [LineView.onCharacterTyped](yarn.unity.lineview.oncharactertyped.md): A Unity Event that is called each time a character is revealed during a typewriter effect.
* [LineView.typewriterEffectSpeed](yarn.unity.lineview.typewritereffectspeed.md): The number of characters per second that should appear during a typewriter effect.
