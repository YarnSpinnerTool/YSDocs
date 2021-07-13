# Instruction.Types.OpCode.CallFunc Field

Calls a function in the client. Pops as many arguments as the
client indicates the function receives, and the result (if any)
is pushed to the stack.		
opA = string: name of the function


```csharp
[OriginalName("CALL_FUNC")]
CallFunc = 12
```



## See Also
* [`Instruction.Types.OpCode`](/api/csharp/yarn/instruction.types.opcode.md): 
The type of instruction that this is.

<div class="class-metadata">

Parent: [`Instruction.Types.OpCode`](/api/csharp/yarn/instruction.types.opcode.md), Namespace: [`Yarn`](/api/csharp/yarn/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [YarnSpinner/YarnSpinner.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.cs#L721), line 721.
