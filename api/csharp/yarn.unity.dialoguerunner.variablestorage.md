# VariableStorage

Property in [DialogueRunner](/api/csharp/yarn.unity.dialoguerunner.md)

## Summary


The variable storage object.


```csharp
public VariableStorageBehaviour VariableStorage
        {
            get => _variableStorage; 
            set
            {
                _variableStorage = value;
                if (_dialogue != null)
                {
                    _dialogue.VariableStorage = value;
                }
            }
        }
```

