# SerializedDictionary&lt;TKey, TValue&gt;

An  that can be serialized as part of a Unity object.

```csharp
public class SerializedDictionary<TKey, TValue> : IDictionary<TKey, TValue>, ISerializationCallbackReceiver
```

## Remarks

Prior to Unity 2020, dictionaries cannot be directly serialized by Unity. This class is a workaround; it provides an API identical to

, and stores its contents as two s: one for `TKey`, and one for `TValue`.

## Type Parameters

| Type Parameter | Description |
| :--- | :--- |
| TKey | The type of key used in the dictionary. |
| TValue | The type of value used in the dictionary. |

## Methods

| Name | Description |
| :--- | :--- |
| [`Add(TKey, TValue)`](serializeddictionary-2.add-0-1.md) |  |
| [`Add(KeyValuePair<TKey, TValue>)`](serializeddictionary-2.add-keyvaluepair-0-1.md) |  |
| [`Clear()`](serializeddictionary-2.clear.md) |  |
| [`Contains(KeyValuePair<TKey, TValue>)`](serializeddictionary-2.contains-keyvaluepair-0-1.md) |  |
| [`ContainsKey(TKey)`](serializeddictionary-2.containskey-0.md) |  |
| [`CopyTo(KeyValuePair<TKey, TValue>[], Int32)`](serializeddictionary-2.copyto-keyvaluepair-0-1-system.int32.md) |  |
| [`GetEnumerator()`](serializeddictionary-2.getenumerator.md) |  |
| [`Remove(TKey)`](serializeddictionary-2.remove-0.md) |  |
| [`Remove(KeyValuePair<TKey, TValue>)`](serializeddictionary-2.remove-keyvaluepair-0-1.md) |  |
| [`TryGetValue(TKey, out TValue)`](serializeddictionary-2.trygetvalue-0-1.md) |  |

## Properties

| Name | Description |
| :--- | :--- |
| [`Count`](serializeddictionary-2.count.md) |  |
| [`IsReadOnly`](serializeddictionary-2.isreadonly.md) |  |
| [`Item[TKey]`](serializeddictionary-2.item-0.md) |  |
| [`Keys`](serializeddictionary-2.keys.md) |  |
| [`Values`](serializeddictionary-2.values.md) |  |

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/SerializedDictionary.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/SerializedDictionary.cs#L24), line 24.

