# SerializedDictionary

Class in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from `IDictionary`2`

## Summary


An  <code>IDictionary&lt;TKey,TValue&gt;</code>  that can be serialized as
part of a Unity object.


```csharp
public class SerializedDictionary<TKey, TValue> : IDictionary<TKey, TValue>, ISerializationCallbackReceiver
```

## Remarks


Prior to Unity 2020, dictionaries cannot be directly serialized by
Unity. This class is a workaround; it provides an API identical to
<code>Dictionary&lt;TKey, TValue&gt;</code> , and stores its contents as
two  <code>List&lt;T&gt;</code> s: one for  <code>TKey</code> ,
and one for  <code>TValue</code> .


## Type Parameters

|Name|Description|
|:---|:---|

## Properties

|Name|Description|
|:---|:---|
|[Count](/api/csharp/yarn.unity.serializeddictionary.count.md)||
|[IsReadOnly](/api/csharp/yarn.unity.serializeddictionary.isreadonly.md)||
|[this[TKey key]](/api/csharp/yarn.unity.serializeddictionary.this[].md)||
|[Keys](/api/csharp/yarn.unity.serializeddictionary.keys.md)||
|[Values](/api/csharp/yarn.unity.serializeddictionary.values.md)||

## Methods

|Name|Description|
|:---|:---|
|[Add(TKey,TValue)](/api/csharp/yarn.unity.serializeddictionary.add-1.md)||
|[Add(KeyValuePair<TKey, TValue>)](/api/csharp/yarn.unity.serializeddictionary.add-2.md)||
|[Clear()](/api/csharp/yarn.unity.serializeddictionary.clear.md)||
|[Contains(KeyValuePair<TKey, TValue>)](/api/csharp/yarn.unity.serializeddictionary.contains.md)||
|[ContainsKey(TKey)](/api/csharp/yarn.unity.serializeddictionary.containskey.md)||
|[CopyTo(KeyValuePair<TKey, TValue>[],int)](/api/csharp/yarn.unity.serializeddictionary.copyto.md)||
|[GetEnumerator()](/api/csharp/yarn.unity.serializeddictionary.getenumerator.md)||
|[Remove(TKey)](/api/csharp/yarn.unity.serializeddictionary.remove-1.md)||
|[Remove(KeyValuePair<TKey, TValue>)](/api/csharp/yarn.unity.serializeddictionary.remove-2.md)||
|[TryGetValue(TKey,TValue)](/api/csharp/yarn.unity.serializeddictionary.trygetvalue.md)||

