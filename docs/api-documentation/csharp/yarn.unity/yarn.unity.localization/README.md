# Localization

Class in [Yarn.Unity](../)

Inherits from `UnityEngine.ScriptableObject`

## Summary

```csharp
public class Localization : ScriptableObject
```

## Methods

| Name                                                                                                                 | Description                                                                                              |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| [AddLocalizedObject(string,T)](yarn.unity.localization.addlocalizedobject.md)                                        |                                                                                                          |
| [AddLocalizedObjects(IEnumerable\<KeyValuePair\<string, T>>)](yarn.unity.localization.addlocalizedobjects.md)        |                                                                                                          |
| [AddLocalizedString(string,string)](yarn.unity.localization.addlocalizedstring.md)                                   | Adds a new string to the runtime string table.                                                           |
| [AddLocalizedStrings(IEnumerable\<KeyValuePair\<string, string>>)](yarn.unity.localization.addlocalizedstrings-1.md) | Adds a collection of strings to the runtime string table.                                                |
| [AddLocalizedStrings(IEnumerable)](yarn.unity.localization.addlocalizedstrings-2.md)                                 | Adds a collection of strings to the runtime string table.                                                |
| [Clear()](yarn.unity.localization.clear.md)                                                                          |                                                                                                          |
| [ContainsLocalizedObject(string)](yarn.unity.localization.containslocalizedobject.md)                                |                                                                                                          |
| [ContainsLocalizedString(string)](yarn.unity.localization.containslocalizedstring.md)                                | Returns a boolean value indicating whether this [Localization](./) contains a string with the given key. |
| [GetLineIDs()](yarn.unity.localization.getlineids.md)                                                                | Gets the line IDs present in this localization.                                                          |
| [GetLocalizedObject(string)](yarn.unity.localization.getlocalizedobject.md)                                          |                                                                                                          |
| [GetLocalizedString(string)](yarn.unity.localization.getlocalizedstring.md)                                          |                                                                                                          |
| [SetLocalizedObject(string,T)](yarn.unity.localization.setlocalizedobject.md)                                        |                                                                                                          |

## Properties

| Name                                                                          | Description                                                                                                                                                      |
| ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ContainsLocalizedAssets](yarn.unity.localization.containslocalizedassets.md) | Gets a value indicating whether this [Localization](./) contains assets that are linked to strings.                                                              |
| [LocaleCode](yarn.unity.localization.localecode.md)                           |                                                                                                                                                                  |
| [UsesAddressableAssets](yarn.unity.localization.usesaddressableassets.md)     | Gets a value indicating whether this [Localization](./) makes use of Addressable Assets ( `true` ), or if it stores its assets as direct references ( `false` ). |
