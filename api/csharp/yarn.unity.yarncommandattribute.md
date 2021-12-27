# YarnCommandAttribute

Class in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from [`YarnActionAttribute`](/api/csharp/yarn.unity.yarnactionattribute.md)

## Summary


An attribute that marks a method on an object as a 
[command]( <![CDATA[ {{<ref
"/docs/unity/working-with-commands">}}]]> ).


```csharp
public class YarnCommandAttribute : YarnActionAttribute
```

## Remarks


When a  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  receives a  <code>Command</code> ,
and no command handler has been installed for the command, it splits it
by spaces, and then checks to see if the second word, if any, is the
name of an object.

By default, it checks for any  <code>GameObject</code> s in the scene.
If one is found, it is checked to see if any of the  <code>MonoBehaviour</code> s attached to the class has a  <a href="yarn.unity.yarncommandattribute.md">YarnCommandAttribute</a>  whose  <a href="yarn.unity.yarncommandattribute.commandstring.md">CommandString</a>  matching the first word
of the command.

If the method is static, it will not try to inject an object.

If a method is found, its parameters are checked:

* If the method takes a single  <code>string</code> [] parameter, the
method is called, and will be passed an array containing all words in
the command after the first two.

* If the method takes a number of parameters equal to the number of
words in the command after the first two, it will be called with those
words as parameters.

* If a parameter is a  <code>GameObject</code> , we look up the object
using  <code>GameObject.Find(string)</code> . As per the API, the game
object must be active.

* If a parameter is assignable to  <code>Component</code> , we will
locate the component based on the name of the object. As per the API of 
<code>GameObject.Find(string)</code> , the game object must be active.
If you'd like to have a custom injector for a parameter, use the
<a href="yarn.unity.yarnparameterattribute.md">YarnParameterAttribute</a> .

* If a parameter is a  <code>bool</code> , the string must be 
<code>true</code>  or  <code>false</code>  (as defined by the standard converter for
<code>string</code>  to  <code>bool</code> ). However, we also allow for
the string to equal the parameter name, case insensitive. This allows
us to write commands with more self-documenting parameters, eg for a
certain  <code>Move(bool wait)</code> , you could write 
<code><![CDATA[<<move wait>>]]></code>  instead of
<code><![CDATA[<<move true>>]]></code> .

* For any other type, we will attempt to convert using
<code>Convert.ChangeType(object, Type, IFormatProvider)</code>  using
the  <code>System.Globalization.CultureInfo.InvariantCulture</code> 
culture. This means that you can implement  <code>IConvertible</code> 
to add new accepted types. (Do be aware that it's a non-CLS compliant
interface, according to its docs. Mono for Unity seems to implement it,
but you may have trouble if you use any other CLS implementation.)

* Otherwise, it will not be called, and a warning will be issued.

### `YarnCommand`s and Coroutines

This attribute may be attached to a coroutine. 

{{|note|}} The  <a href="yarn.unity.dialoguerunner.md">DialogueRunner</a>  determines if the method is
a coroutine if the method returns  <code>IEnumerator</code> . 
{{|/note|}}

If the method is a coroutine, the DialogueRunner will pause execution
until the coroutine ends.


## Properties

|Name|Description|
|:---|:---|
|[CommandString](/api/csharp/yarn.unity.yarncommandattribute.commandstring.md)||
|[Injector](/api/csharp/yarn.unity.yarncommandattribute.injector.md)|Override the state injector for this command only.|

