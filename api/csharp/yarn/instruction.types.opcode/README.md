# Instruction.Types.OpCode

The type of instruction that this is.

```csharp
public enum OpCode
```

## Fields

| Name | Description |
| :--- | :--- |
| [`AddOption`](instruction.types.opcode.addoption.md) | Adds an entry to the option list \(see ShowOptions\). - opA = string: string ID for option to add - opB = string: destination to go to if this option is selected - opC = number: number of expressions on the stack to insert into the line - opD = bool: whether the option has a condition on it \(in which case a value should be popped off the stack and used to signal the game that the option should be not available\) |
| [`CallFunc`](instruction.types.opcode.callfunc.md) | Calls a function in the client. Pops as many arguments as the client indicates the function receives, and the result \(if any\) is pushed to the stack.         opA = string: name of the function |
| [`Jump`](instruction.types.opcode.jump.md) | Peeks a string from stack, and jumps to that named position in the node.  No operands. |
| [`JumpIfFalse`](instruction.types.opcode.jumpiffalse.md) | Jumps to the named position in the the node, if the top of the stack is not null, zero or false. opA = string: label name |
| [`JumpTo`](instruction.types.opcode.jumpto.md) | Jumps to a named position in the node. opA = string: label name |
| [`Pop`](instruction.types.opcode.pop.md) | Discards top of stack. No operands. |
| [`PushBool`](instruction.types.opcode.pushbool.md) | Pushes a boolean onto the stack. opA = bool: the bool to push to stack |
| [`PushFloat`](instruction.types.opcode.pushfloat.md) | Pushes a floating point number onto the stack. opA = float: number to push to stack |
| [`PushNull`](instruction.types.opcode.pushnull.md) | Pushes a null value onto the stack. No operands. |
| [`PushString`](instruction.types.opcode.pushstring.md) | Pushes a string onto the stack. opA = string: the string to push to the stack. |
| [`PushVariable`](instruction.types.opcode.pushvariable.md) | Pushes the contents of a variable onto the stack. opA = name of variable |
| [`RunCommand`](instruction.types.opcode.runcommand.md) | Delivers a command to the client. opA = string: command text |
| [`RunLine`](instruction.types.opcode.runline.md) | Delivers a string ID to the client. opA = string: string ID |
| [`RunNode`](instruction.types.opcode.runnode.md) | Pops a string off the top of the stack, and runs the node with that name. No operands. |
| [`ShowOptions`](instruction.types.opcode.showoptions.md) | Presents the current list of options to the client, then clears the list. The most recently selected option will be on the top of the stack when execution resumes. No operands. |
| [`Stop`](instruction.types.opcode.stop.md) | Stops execution of the program. No operands. |
| [`StoreVariable`](instruction.types.opcode.storevariable.md) | Stores the contents of the top of the stack in the named variable.  opA = name of variable |

## Namespace

[`Yarn`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [YarnSpinner/YarnSpinner.cs](https://github.com/YarnSpinnerTool/YarnSpinner//blob/develop/YarnSpinner/YarnSpinner.cs#L644), line 644.

