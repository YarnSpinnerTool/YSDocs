# YarnFunctionAttribute

Class in [Yarn.Unity](./)

Inherits from [`YarnActionAttribute`](yarn.unity.yarnactionattribute/)

## Summary

Marks the method as a function to be registered with the running instance's library.

```csharp
public class YarnFunctionAttribute : YarnActionAttribute
```

## Remarks

See [RegisterFunction(string,Delegate)](../yarn/yarn.library/yarn.library.registerfunction-7.md) and the generic overloads for what is and is not valid.

This will throw an error if you attempt to add a function that has more than 16 parameters, as that is the largest overload that ``System.Func`1`` etc has.

Yarn Spinner for Unity finds methods with the YarnFunction attribute by reading your source code. If your project uses Unity 2021.1 or earlier, you will need to tell Yarn Spinner for Unity to do this manually, by opening the Window method and choosing Yarn Spinner -> Update Yarn Commands. You don't need to do this on later versions of Unity, as it will be done for you automatically when your code compiles.
