# LineView.useTypewriterEffect

Field in [LineView](/docs/api/csharp/yarn.unity.lineview.md)

## Summary


Controls whether the text of  <a href="yarn.unity.lineview.linetext.md">lineText</a>  should be
gradually revealed over time.


```csharp
public bool useTypewriterEffect = false;
```

## Remarks

<p>If this value is <code>true</code>, the <a href="yarn.unity.lineview.linetext.md">lineText</a> object's <code>TMPro.TMP_Text.maxVisibleCharacters</code> property will animate from 0
to the length of the text, at a rate of <a href="yarn.unity.lineview.typewritereffectspeed.md">typewriterEffectSpeed</a> letters per second when the line
appears. <a href="yarn.unity.lineview.oncharactertyped.md">onCharacterTyped</a> is called for every new
character that is revealed.</p> <p>If this value is <code>false</code>, the <a href="yarn.unity.lineview.linetext.md">lineText</a> will all be revealed at the same time.</p> <p>
{% hint style="note" %}
If <a href="yarn.unity.lineview.usefadeeffect.md">useFadeEffect</a> is <code>true</code>, the typewriter effect will run after the fade-in
is complete.
{% endhint %}
</p>

## See Also

* [LineView.lineText](/docs/api/csharp/yarn.unity.lineview.linetext.md): The  <code>TMPro.TextMeshProUGUI</code>  object that displays the text of dialogue lines.
* [LineView.onCharacterTyped](/docs/api/csharp/yarn.unity.lineview.oncharactertyped.md): A Unity Event that is called each time a character is revealed during a typewriter effect.
* [LineView.typewriterEffectSpeed](/docs/api/csharp/yarn.unity.lineview.typewritereffectspeed.md): The number of characters per second that should appear during a typewriter effect.

