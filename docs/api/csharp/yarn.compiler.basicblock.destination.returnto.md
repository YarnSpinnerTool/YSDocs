# ReturnTo

Property in [Destination](yarn.compiler.basicblock.destination.md)

## Summary

When this destination is taken, if this value is non-null, a VM should push this block onto the call stack. When a Return instruction is reached, pop a block off the call stack and return to it. If the value is null, the VM should clear the call stack.

```csharp
public BasicBlock? ReturnTo { get; set; }
```
