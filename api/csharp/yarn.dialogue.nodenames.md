# NodeNames

Property in [Dialogue](/api/csharp/yarn.dialogue.md)

## Summary


Gets the names of the nodes in the currently loaded Program.


```csharp
public IEnumerable<string> NodeNames
        {
            get
            {
                return this.Program.Nodes.Keys;
            }
        }
```

