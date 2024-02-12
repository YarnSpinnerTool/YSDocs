# YarnCommandAttribute

Class in [Yarn.Unity](../)

Inherits from [`YarnActionAttribute`](../yarn.unity.yarnactionattribute/)

## Summary

An attribute that marks a method on an object as a command.

```csharp
public class YarnCommandAttribute : YarnActionAttribute
```

## Remarks

When a [DialogueRunner](../yarn.unity.dialoguerunner/) receives a [Command](../../yarn/yarn.command/), and no command handler has been installed for the command, it splits it by spaces, and then checks to see if the second word, if any, is the name of an object.

By default, it checks for any `UnityEngine.GameObject`s in the scene. If one is found, it is checked to see if any of the `UnityEngine.MonoBehaviour`s attached to the class has a [YarnCommandAttribute](./) whose `YarnCommandAttribute.CommandString` matching the first word of the command.

If the method is static, it will not try to inject an object.

If a method is found, its parameters are checked:

* If the method takes a single `string`\[] parameter, the method is called, and will be passed an array containing all words in the command after the first two.
* If the method takes a number of parameters equal to the number of words in the command after the first two, it will be called with those words as parameters.
* If a parameter is a `UnityEngine.GameObject`, we look up the object using `UnityEngine.GameObject.Find(System.String)`. As per the API, the game object must be active.
* If a parameter is assignable to `UnityEngine.Component`, we will locate the component based on the name of the object. As per the API of `UnityEngine.GameObject.Find(System.String)`, the game object must be active. If you'd like to have a custom injector for a parameter, use the [YarnParameterAttribute](../yarn.unity.yarnparameterattribute/).
* If a parameter is a `bool`, the string must be `true` or `false` (as defined by the standard converter for `string` to `bool`). However, we also allow for the string to equal the parameter name, case insensitive. This allows us to write commands with more self-documenting parameters, eg for a certain `Move(bool wait)`, you could write `<<move wait>>` instead of `<<move true>>`.
* For any other type, we will attempt to convert using `System.Convert.ChangeType(System.Object,System.Type,System.IFormatProvider)` using the `System.Globalization.CultureInfo.InvariantCulture` culture. This means that you can implement `System.IConvertible` to add new accepted types. (Do be aware that it's a non-CLS compliant interface, according to its docs. Mono for Unity seems to implement it, but you may have trouble if you use any other CLS implementation.)
* Otherwise, it will not be called, and a warning will be issued.

This attribute may be attached to a coroutine.

{% hint style="info" %}
The [DialogueRunner](../yarn.unity.dialoguerunner/) determines if the method is a coroutine if the method returns `System.Collections.IEnumerator`, or if the method returns a `UnityEngine.Coroutine`.
{% endhint %}

If the method is a coroutine, or returns a `UnityEngine.Coroutine`, the DialogueRunner will pause execution until the coroutine ends.

Yarn Spinner for Unity finds methods with the YarnCommand attribute by reading your source code. If your project uses Unity 2021.1 or earlier, you will need to tell Yarn Spinner for Unity to do this manually, by opening the Window method and choosing Yarn Spinner -> Update Yarn Commands. You don't need to do this on later versions of Unity, as it will be done for you automatically when your code compiles.

## Properties

| Name                                                    | Description                                        |
| ------------------------------------------------------- | -------------------------------------------------- |
| [Injector](yarn.unity.yarncommandattribute.injector.md) | Override the state injector for this command only. |
