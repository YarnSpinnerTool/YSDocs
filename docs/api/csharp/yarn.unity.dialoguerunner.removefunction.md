# RemoveFunction(string)

Method in [DialogueRunner](yarn.unity.dialoguerunner.md)

## Summary

Remove a registered function.

```csharp
public void RemoveFunction(string name);
```

## Remarks

After a function has been removed, it cannot be called from Yarn scripts.

## Parameters

| Name          | Description                         |
| ------------- | ----------------------------------- |
| `string` name | The name of the function to remove. |

## See Also

* [DialogueRunner.AddFunction(string,System.Func\<TResult>)](yarn.unity.dialoguerunner.addfunction-2.md): Add a new function that returns a value, so that it can be called from Yarn scripts.
