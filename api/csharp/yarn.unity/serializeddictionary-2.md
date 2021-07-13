# SerializedDictionary<TKey, TValue> Class

An <see cref="!:IDictionary<TKey,TValue>"></see> that can be serialized as
part of a Unity object.


```csharp
public class SerializedDictionary<TKey, TValue> : IDictionary<TKey, TValue>, ISerializationCallbackReceiver
```
## Remarks

Prior to Unity 2020, dictionaries cannot be directly serialized by
Unity. This class is a workaround; it provides an API identical to
<see cref="!:Dictionary<TKey, TValue>"></see>, and stores its contents as
two <see cref="!:List<T>"></see>s: one for <code data-dev-comment-type="typeparamref" class="typeparamref">TKey</code>,
and one for <code data-dev-comment-type="typeparamref" class="typeparamref">TValue</code>.


## Type Parameters
|Type Parameter|Description|
|:---|:---|
|TKey|The type of key used in the dictionary.|
|TValue|The type of value used in the dictionary.|


## Methods
|Name|Description|
|:---|:---|
|[Add(TKey, TValue)](/api/csharp/yarn.unity/serializeddictionary-2.add--0,-1-.md)||
|[Add(KeyValuePair<TKey, TValue>)](/api/csharp/yarn.unity/serializeddictionary-2.add-keyvaluepair--0,-1--.md)||
|[Clear()](/api/csharp/yarn.unity/serializeddictionary-2.clear.md)||
|[Contains(KeyValuePair<TKey, TValue>)](/api/csharp/yarn.unity/serializeddictionary-2.contains-keyvaluepair--0,-1--.md)||
|[ContainsKey(TKey)](/api/csharp/yarn.unity/serializeddictionary-2.containskey--0-.md)||
|[CopyTo(KeyValuePair<TKey, TValue>[], Int32)](/api/csharp/yarn.unity/serializeddictionary-2.copyto-keyvaluepair--0,-1---,system.int32-.md)||
|[GetEnumerator()](/api/csharp/yarn.unity/serializeddictionary-2.getenumerator.md)||
|[Remove(TKey)](/api/csharp/yarn.unity/serializeddictionary-2.remove--0-.md)||
|[Remove(KeyValuePair<TKey, TValue>)](/api/csharp/yarn.unity/serializeddictionary-2.remove-keyvaluepair--0,-1--.md)||
|[TryGetValue(TKey, out TValue)](/api/csharp/yarn.unity/serializeddictionary-2.trygetvalue--0,-1@-.md)||
## Properties
|Name|Description|
|:---|:---|
|[Count](/api/csharp/yarn.unity/serializeddictionary-2.count.md)||
|[IsReadOnly](/api/csharp/yarn.unity/serializeddictionary-2.isreadonly.md)||
|[Item[TKey]](/api/csharp/yarn.unity/serializeddictionary-2.item--0-.md)||
|[Keys](/api/csharp/yarn.unity/serializeddictionary-2.keys.md)||
|[Values](/api/csharp/yarn.unity/serializeddictionary-2.values.md)||
<div class="class-metadata">

Namespace: [`Yarn.Unity`](/api/csharp/yarn.unity/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/SerializedDictionary.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/SerializedDictionary.cs#L24), line 24.
