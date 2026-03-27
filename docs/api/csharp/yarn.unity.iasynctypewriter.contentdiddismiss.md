# IAsyncTypewriter.ContentDidDismiss()

Method in [IAsyncTypewriter](/docs/api/csharp/yarn.unity.iasynctypewriter.md)

## Summary


Called after the content has been visibly hidden.


```csharp
public void ContentDidDismiss();
```

## Remarks


This is the typewriters last chance to do any cleanup that they may need to do before more content or full destruction occurs, will always be called after  <a href="yarn.unity.iasynctypewriter.contentwilldismiss.md">ContentWillDismiss()</a> .
It is the responsibility of the  <a href="yarn.unity.dialoguepresenterbase.md">DialoguePresenterBase</a>  to only call this after hiding anything that might look weird if state is reset.


