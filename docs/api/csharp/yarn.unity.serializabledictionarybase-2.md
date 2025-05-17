# SerializableDictionaryBase

Class in [Yarn.Unity](/docs/api/csharp/yarn.unity.md)

Inherits from [`SerializableDictionaryBase`](/docs/api/csharp/yarn.unity.serializabledictionarybase-1.md)

## Summary



```csharp
public abstract class SerializableDictionaryBase<TKey, TValue, TValueStorage> : SerializableDictionaryBase, IDictionary<TKey, TValue>, IDictionary, ISerializationCallbackReceiver, IDeserializationCallback, ISerializable
```

## Constructors

|Name|Description|
|:---|:---|
|[SerializableDictionaryBase()](/docs/api/csharp/yarn.unity.serializabledictionarybase..ctor-1.md)||
|[SerializableDictionaryBase(IDictionary<TKey, TValue>)](/docs/api/csharp/yarn.unity.serializabledictionarybase..ctor-2.md)||

## Indexers

|Name|Description|
|:---|:---|
|[this[TKey key]](/docs/api/csharp/yarn.unity.serializabledictionarybase.this[]-1.md)||
|[this[object key]](/docs/api/csharp/yarn.unity.serializabledictionarybase.this[]-2.md)||

## Methods

|Name|Description|
|:---|:---|
|[Add(TKey,TValue)](/docs/api/csharp/yarn.unity.serializabledictionarybase.add-1.md)||
|[Add(KeyValuePair<TKey, TValue>)](/docs/api/csharp/yarn.unity.serializabledictionarybase.add-2.md)||
|[Add(object,object)](/docs/api/csharp/yarn.unity.serializabledictionarybase.add-3.md)||
|[Clear()](/docs/api/csharp/yarn.unity.serializabledictionarybase.clear.md)||
|[Contains(KeyValuePair<TKey, TValue>)](/docs/api/csharp/yarn.unity.serializabledictionarybase.contains-1.md)||
|[Contains(object)](/docs/api/csharp/yarn.unity.serializabledictionarybase.contains-2.md)||
|[ContainsKey(TKey)](/docs/api/csharp/yarn.unity.serializabledictionarybase.containskey.md)||
|[CopyFrom(IDictionary<TKey, TValue>)](/docs/api/csharp/yarn.unity.serializabledictionarybase.copyfrom.md)||
|[CopyTo(Array,int)](/docs/api/csharp/yarn.unity.serializabledictionarybase.copyto-2.md)||
|[CopyTo(KeyValuePair<TKey, TValue>[],int)](/docs/api/csharp/yarn.unity.serializabledictionarybase.copyto-1.md)||
|[GetEnumerator()](/docs/api/csharp/yarn.unity.serializabledictionarybase.getenumerator.md)||
|[GetObjectData(SerializationInfo,StreamingContext)](/docs/api/csharp/yarn.unity.serializabledictionarybase.getobjectdata.md)||
|[OnAfterDeserialize()](/docs/api/csharp/yarn.unity.serializabledictionarybase.onafterdeserialize.md)||
|[OnBeforeSerialize()](/docs/api/csharp/yarn.unity.serializabledictionarybase.onbeforeserialize.md)||
|[OnDeserialization(object)](/docs/api/csharp/yarn.unity.serializabledictionarybase.ondeserialization.md)||
|[Remove(TKey)](/docs/api/csharp/yarn.unity.serializabledictionarybase.remove-1.md)||
|[Remove(KeyValuePair<TKey, TValue>)](/docs/api/csharp/yarn.unity.serializabledictionarybase.remove-2.md)||
|[Remove(object)](/docs/api/csharp/yarn.unity.serializabledictionarybase.remove-3.md)||
|[TryGetValue(TKey,TValue)](/docs/api/csharp/yarn.unity.serializabledictionarybase.trygetvalue.md)||

## Properties

|Name|Description|
|:---|:---|
|[Count](/docs/api/csharp/yarn.unity.serializabledictionarybase.count.md)||
|[IsFixedSize](/docs/api/csharp/yarn.unity.serializabledictionarybase.isfixedsize.md)||
|[IsReadOnly](/docs/api/csharp/yarn.unity.serializabledictionarybase.isreadonly.md)||
|[IsSynchronized](/docs/api/csharp/yarn.unity.serializabledictionarybase.issynchronized.md)||
|[Keys](/docs/api/csharp/yarn.unity.serializabledictionarybase.keys.md)||
|[SyncRoot](/docs/api/csharp/yarn.unity.serializabledictionarybase.syncroot.md)||
|[Values](/docs/api/csharp/yarn.unity.serializabledictionarybase.values.md)||

