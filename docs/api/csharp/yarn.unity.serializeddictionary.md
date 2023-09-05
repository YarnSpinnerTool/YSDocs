# SerializedDictionary

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

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
|[this[TKey key]](/docs/api/csharp/yarn.unity.serializeddictionary.this[].md)||

## Methods

|Name|Description|
|:---|:---|
|[Add(TKey,TValue)](/docs/api/csharp/yarn.unity.serializeddictionary.add-1.md)||
|[Add(KeyValuePair<TKey, TValue>)](/docs/api/csharp/yarn.unity.serializeddictionary.add-2.md)||
|[Clear()](/docs/api/csharp/yarn.unity.serializeddictionary.clear.md)||
|[Contains(KeyValuePair<TKey, TValue>)](/docs/api/csharp/yarn.unity.serializeddictionary.contains.md)||
|[ContainsKey(TKey)](/docs/api/csharp/yarn.unity.serializeddictionary.containskey.md)||
|[CopyTo(KeyValuePair<TKey, TValue>[],int)](/docs/api/csharp/yarn.unity.serializeddictionary.copyto.md)||
|[GetEnumerator()](/docs/api/csharp/yarn.unity.serializeddictionary.getenumerator.md)||
|[Remove(TKey)](/docs/api/csharp/yarn.unity.serializeddictionary.remove-1.md)||
|[Remove(KeyValuePair<TKey, TValue>)](/docs/api/csharp/yarn.unity.serializeddictionary.remove-2.md)||
|[TryGetValue(TKey,TValue)](/docs/api/csharp/yarn.unity.serializeddictionary.trygetvalue.md)||

## Properties

|Name|Description|
|:---|:---|
|[Count](/docs/api/csharp/yarn.unity.serializeddictionary.count.md)||
|[IsReadOnly](/docs/api/csharp/yarn.unity.serializeddictionary.isreadonly.md)||
|[Keys](/docs/api/csharp/yarn.unity.serializeddictionary.keys.md)||
|[Values](/docs/api/csharp/yarn.unity.serializeddictionary.values.md)||

