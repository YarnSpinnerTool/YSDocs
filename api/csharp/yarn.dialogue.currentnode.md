# CurrentNode

Property in [Dialogue](/api/csharp/yarn.dialogue.md)

## Summary


Gets the name of the node that this Dialogue is currently
executing.


```csharp
public string CurrentNode
        {
            get
            {
                if (this.vm == null)
                {
                    return null;
                }
                else
                {
                    return this.vm.currentNodeName;
                }
            }
        }
```

## Remarks

If  <a href="yarn.dialogue.continue.md">Continue()</a>  has never been called, this
value will be `null`.

