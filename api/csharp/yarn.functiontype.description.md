# Description

Property in [FunctionType](/api/csharp/yarn.functiontype.md)

## Summary


Gets a more verbose description of this type.


```csharp
public string Description
        {
            get
            {
                List<string> parameterNames = new List<string>();
                foreach (var param in this.Parameters)
                {
                    if (param == null)
                    {
                        parameterNames.Add("Undefined");
                    }
                    else
                    {
                        parameterNames.Add(param.Name);
                    }
                }

                var returnTypeName = this.ReturnType?.Name ?? "Undefined";

                return $"({string.Join(", ", parameterNames)}) -> {returnTypeName}";
            }

            set
            {
                throw new System.InvalidOperationException();
            }
        }
```

