# YarnCommandAttribute

Class in [Yarn.Unity](yarn.unity.md)

Inherits from [`YarnActionAttribute`](yarn.unity.yarnactionattribute.md)

## Summary

An attribute that marks a method on an object as a command.

```csharp
public class YarnCommandAttribute : YarnActionAttribute
```

## Remarks

When a [DialogueRunner](yarn.unity.dialoguerunner.md) receives a [Command](yarn.command.md),\
and no command handler has been installed for the command, it splits it\
by spaces, and then checks to see if the second word, if any, is the\
name of an object.

By default, it checks for any `UnityEngine.GameObject`s in the scene. If\
one is found, it is checked to see if any of the `UnityEngine.MonoBehaviour`s attached to the class has a [YarnCommandAttribute](yarn.unity.yarncommandattribute.md) whose [Name](yarn.unity.yarnactionattribute.name.md) matches the first word of the command.

If the method is static, it will not try to use an object.

If a method is found, its parameters are checked:

* If the method takes a single `string`\[] parameter, the\
  method is called, and will be passed an array containing all words in\
  the command after the first two.
* If the method takes a number of parameters equal to the number of words\
  in the command after the first two, it will be called with those words\
  as parameters.
* If a parameter is a `UnityEngine.GameObject`, we look up the object\
  using `UnityEngine.GameObject.Find(System.String)`. As per the API, the game\
  object must be active.
* If a parameter is assignable to `UnityEngine.Component`, we will locate\
  the component based on the name of the object. As per the API of `UnityEngine.GameObject.Find(System.String)`, the game object must be active.
* If a parameter is a `bool`, the string must be `true`\
  or `false` (as defined by the standard converter for `string` to `bool`). However, we also allow for the\
  string to equal the parameter name, case insensitive. This allows us to\
  write commands with more self-documenting parameters, eg for a certain`Move(bool wait)`, you could write `<<move wait>>`\
  instead of `<<move true>>`.
* For any other type, we will attempt to convert using `System.Convert.ChangeType(System.Object,System.Type,System.IFormatProvider)` using the`System.Globalization.CultureInfo.InvariantCulture` culture.\
  This means that you can implement `System.IConvertible` to add new\
  accepted types. (Do be aware that it's a non-CLS compliant interface,\
  according to its docs. Mono for Unity seems to implement it, but you may\
  have trouble if you use any other CLS implementation.)
* Otherwise, it will not be called, and a warning will be\
  issued.

This attribute may be attached to a coroutine or to an async\
method.

{% hint style="info" %}
The [DialogueRunner](yarn.unity.dialoguerunner.md) determines if the method is a coroutine\
if the method returns `System.Collections.IEnumerator`, or if the method\
returns a `UnityEngine.Coroutine` or a task.
{% endhint %}

If the method is a coroutine, returns a `UnityEngine.Coroutine`, or\
returns a task, the DialogueRunner will pause execution until the the\
coroutine or task ends.
