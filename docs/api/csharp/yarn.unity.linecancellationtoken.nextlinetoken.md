# LineCancellationToken.NextLineToken

Property in [LineCancellationToken](/docs/api/csharp/yarn.unity.linecancellationtoken.md)

{% hint style="warning" %}
This property is <b>obsolete</b> and may be removed from a future version of Yarn Spinner: Please use NextContentToken instead.
{% endhint %}

## Summary


A  <code>System.Threading.CancellationToken</code>  that becomes cancelled when a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  wishes all dialogue presenters to stop running
the current line. For example, on-screen UI should be dismissed, and
any ongoing audio playback should be stopped.


```csharp
public readonly CancellationToken NextLineToken { get }
```

