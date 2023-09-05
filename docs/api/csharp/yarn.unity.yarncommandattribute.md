# YarnCommandAttribute

Class in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from [`YarnActionAttribute`](/api/csharp/yarn.unity.yarnactionattribute.md)

## Summary


An attribute that marks a method on an object as a command.


```csharp
public class YarnCommandAttribute : YarnActionAttribute
```

## Remarks

<p>
When a <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> receives a <a href="yarn.command.md">Command</a>,
and no command handler has been installed for the command, it splits it
by spaces, and then checks to see if the second word, if any, is the
name of an object.
</p> <p>
By default, it checks for any <code>UnityEngine.GameObject</code>s in the scene. If
one is found, it is checked to see if any of the <code>UnityEngine.MonoBehaviour</code>s attached to the class has a <a href="yarn.unity.yarncommandattribute.md">YarnCommandAttribute</a> whose <a href="yarn.unity.yarncommandattribute.commandstring.md">CommandString</a> matching the first word of
the command.
</p> <p>If the method is static, it will not try to inject an
object.</p> <p>If a method is found, its parameters are checked:</p> <ul type="bullet">
<li>
If the method takes a single <code>string</code>[] parameter, the
method is called, and will be passed an array containing all words in
the command after the first two.
</li>
<li>
If the method takes a number of parameters equal to the number of words
in the command after the first two, it will be called with those words
as parameters.
</li>
<li>
If a parameter is a <code>UnityEngine.GameObject</code>, we look up the object
using <code>UnityEngine.GameObject.Find(System.String)</code>. As per the API, the game
object must be active.
</li>
<li>
If a parameter is assignable to <code>UnityEngine.Component</code>, we will locate
the component based on the name of the object. As per the API of <code>UnityEngine.GameObject.Find(System.String)</code>, the game object must be active. If
you'd like to have a custom injector for a parameter, use the <a href="yarn.unity.yarnparameterattribute.md">YarnParameterAttribute</a>.
</li>
<li>
If a parameter is a <code>bool</code>, the string must be <code>true</code>
or <code>false</code> (as defined by the standard converter for <code>string</code> to <code>bool</code>). However, we also allow for the
string to equal the parameter name, case insensitive. This allows us to
write commands with more self-documenting parameters, eg for a certain
<code>Move(bool wait)</code>, you could write <code>&lt;&lt;move wait&gt;&gt;</code>
instead of <code>&lt;&lt;move true&gt;&gt;</code>.
</li>
<li>
For any other type, we will attempt to convert using <code>System.Convert.ChangeType(System.Object,System.Type,System.IFormatProvider)</code> using the
<code>System.Globalization.CultureInfo.InvariantCulture</code> culture.
This means that you can implement <code>System.IConvertible</code> to add new
accepted types. (Do be aware that it's a non-CLS compliant interface,
according to its docs. Mono for Unity seems to implement it, but you may
have trouble if you use any other CLS implementation.)
</li>
<li>Otherwise, it will not be called, and a warning will be
issued.</li>
</ul> <p>This attribute may be attached to a coroutine. </p> <p>
{% hint style="note" %}

The <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a> determines if the method is a coroutine
if the method returns <code>System.Collections.IEnumerator</code>, or if the method
returns a <code>UnityEngine.Coroutine</code>. 

{% endhint %}
</p> <p>
If the method is a coroutine, or returns a <code>UnityEngine.Coroutine</code>, the
DialogueRunner will pause execution until the coroutine ends.
</p> <p>
Yarn Spinner for Unity finds methods with the YarnCommand attribute by
reading your source code. If your project uses Unity 2021.1 or earlier,
you will need to tell Yarn Spinner for Unity to do this manually, by
opening the Window method and choosing Yarn Spinner -&gt; Update Yarn
Commands. You don't need to do this on later versions of Unity, as it
will be done for you automatically when your code compiles.
</p>

## Properties

|Name|Description|
|:---|:---|
|[CommandString](/api/csharp/yarn.unity.yarncommandattribute.commandstring.md)||
|[Injector](/api/csharp/yarn.unity.yarncommandattribute.injector.md)|Override the state injector for this command only.|

