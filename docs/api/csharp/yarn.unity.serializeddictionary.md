# SerializedDictionary

Class in [Yarn.Unity](yarn.unity.md)

Inherits from `System.Object`

## Summary

An ``System.Collections.Generic.IDictionary`2`` that can be serialized as part of a Unity object.

```csharp
public class SerializedDictionary<TKey, TValue> : IDictionary<TKey, TValue>, ISerializationCallbackReceiver
```

## Remarks

Prior to Unity 2020, dictionaries cannot be directly serialized by Unity. This class is a workaround; it provides an API identical to `System.Collections.Generic.Dictionary2</code> , and stores its contents as two <code>System.Collections.Generic.List1` s: one for `TKey` , and one for `TValue` .

## Type Parameters

| Name   | Description                               |
| ------ | ----------------------------------------- |
| TKey   | The type of key used in the dictionary.   |
| TValue | The type of value used in the dictionary. |

## Indexers

| Name                                                           | Description |
| -------------------------------------------------------------- | ----------- |
| [this\[TKey key\]](yarn.unity.serializeddictionary.this\[].md) |             |

## Methods

| Name                                                                                     | Description |
| ---------------------------------------------------------------------------------------- | ----------- |
| [Add(TKey,TValue)](yarn.unity.serializeddictionary.add-1.md)                             |             |
| [Add(KeyValuePair\<TKey, TValue>)](yarn.unity.serializeddictionary.add-2.md)             |             |
| [Clear()](yarn.unity.serializeddictionary.clear.md)                                      |             |
| [Contains(KeyValuePair\<TKey, TValue>)](yarn.unity.serializeddictionary.contains.md)     |             |
| [ContainsKey(TKey)](yarn.unity.serializeddictionary.containskey.md)                      |             |
| [CopyTo(KeyValuePair\<TKey, TValue>\[\],int)](yarn.unity.serializeddictionary.copyto.md) |             |
| [GetEnumerator()](yarn.unity.serializeddictionary.getenumerator.md)                      |             |
| [Remove(TKey)](yarn.unity.serializeddictionary.remove-1.md)                              |             |
| [Remove(KeyValuePair\<TKey, TValue>)](yarn.unity.serializeddictionary.remove-2.md)       |             |
| [TryGetValue(TKey,TValue)](yarn.unity.serializeddictionary.trygetvalue.md)               |             |

## Properties

| Name                                                        | Description |
| ----------------------------------------------------------- | ----------- |
| [Count](yarn.unity.serializeddictionary.count.md)           |             |
| [IsReadOnly](yarn.unity.serializeddictionary.isreadonly.md) |             |
| [Keys](yarn.unity.serializeddictionary.keys.md)             |             |
| [Values](yarn.unity.serializeddictionary.values.md)         |             |
