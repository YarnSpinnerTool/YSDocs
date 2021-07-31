# Culture

Holds information about a language.

```csharp
public struct Culture
```

## Fields

| Name | Description |
| :--- | :--- |
| [`DisplayName`](culture.displayname.md) | The display name of a language. Will be "German \(Switzerland\)" for "de-CH". Use this value to present the language in an English UI. |
| [`Name`](culture.name.md) | The unique language ID used to identify a language as RFC 4646. Will be "de-CH" for "German \(Switzerland\)". Use this for storing settings or identifying a language. |
| [`NativeName`](culture.nativename.md) | The languages name as called in the language itself. Will be "Deutsch \(Schweiz\) for "de-CH". Use this to present the language in-game so people can find their native language. |

## Namespace

[`Yarn.Unity`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Runtime/Culture.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Runtime/Culture.cs#L8), line 8.

