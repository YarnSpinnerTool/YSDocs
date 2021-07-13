# Instruction.Types.OpCode.AddOption Field

Adds an entry to the option list (see ShowOptions).
- opA = string: string ID for option to add
- opB = string: destination to go to if this option is selected
- opC = number: number of expressions on the stack to insert
into the line
- opD = bool: whether the option has a condition on it (in which
case a value should be popped off the stack and used to signal
the game that the option should be not available)


```csharp
[OriginalName("ADD_OPTION")]
AddOption = 4
```



## See Also
* [`Instruction.Types.OpCode`](/api/csharp/yarn/instruction.types.opcode.md): 
The type of instruction that this is.

## Namespace
[`Yarn`](/api/csharp/yarn/README.md)

## Assembly
YarnSpinner.dll

## Source
Defined in [YarnSpinner/YarnSpinner.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.cs#L676), line 676.
