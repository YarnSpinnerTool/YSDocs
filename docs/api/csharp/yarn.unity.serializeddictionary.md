# SerializedDictionary

Class in [Yarn.Unity](/api/csharp/yarn.unity.md)

Inherits from `System.Object`

## Summary


An  <code>System.Collections.Generic.IDictionary`2</code>  that can be serialized as
part of a Unity object.


```csharp
public class SerializedDictionary<TKey, TValue> : IDictionary<TKey, TValue>, ISerializationCallbackReceiver
```

## Remarks


Prior to Unity 2020, dictionaries cannot be directly serialized by
Unity. This class is a workaround; it provides an API identical to
<code>System.Collections.Generic.Dictionary`2</code> , and stores its contents as
two  <code>System.Collections.Generic.List`1</code> s: one for  <code>TKey</code> ,
and one for  <code>TValue</code> .


## Type Parameters

|Name|Description|
|:---|:---|
|TKey|The type of key used in the dictionary.|
|TValue|The type of value used in the dictionary.|

## Indexers

|Name|Description|
|:---|:---|
|[this[TKey key]](/api/csharp/yarn.unity.serializeddictionary.this[].md)||

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

## Properties

|Name|Description|
|:---|:---|
|[Count](/api/csharp/yarn.unity.serializeddictionary.count.md)||
|[IsReadOnly](/api/csharp/yarn.unity.serializeddictionary.isreadonly.md)||
|[Keys](/api/csharp/yarn.unity.serializeddictionary.keys.md)||
|[Values](/api/csharp/yarn.unity.serializeddictionary.values.md)||

