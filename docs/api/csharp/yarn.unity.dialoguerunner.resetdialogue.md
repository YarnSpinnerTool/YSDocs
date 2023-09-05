# DialogueRunner.ResetDialogue(string)

Method in [DialogueRunner](/api/csharp/yarn.unity.dialoguerunner.md)

{% hint style="warning" %}
This method is <b>obsolete</b> and may be removed from a future version of Yarn Spinner.
{% endhint %}

## Summary


Starts running the dialogue again.


```csharp
public void ResetDialogue(string nodeName = null)
```

## Remarks


If  <code>nodeName</code>  is null, the node specified by
<a href="yarn.unity.dialoguerunner.startnode.md">startNode</a>  is attempted, followed the currently
running node. If none of these options are available, an  <code>System.ArgumentNullException</code>  is thrown.


## Parameters

|Name|Description|
|:---|:---|
|`string` nodeName||

