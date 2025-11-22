# InputSystemAvailability.GetKeyDown(KeyCode)

Method in [InputSystemAvailability](/docs/api/csharp/yarn.unity.inputsystemavailability.md)

## Summary


Gets a value indicating whether the key indicated by a  <code>UnityEngine.KeyCode</code>  was pressed this frame.


```csharp
public static bool GetKeyDown(KeyCode key)
```

## Remarks


If the Legacy Input Manager is enabled, this method wraps  <code>UnityEngine.Input.GetKeyDown(UnityEngine.KeyCode)</code> . Otherwise, it attempts to find the  <code>UnityEngine.InputSystem.Key</code>  equivalent of  <code>key</code> , and then checks with  <code>UnityEngine.InputSystem.Keyboard.current</code>  to find the key,
and queries its  <code>UnityEngine.InputSystem.Controls.ButtonControl.wasPressedThisFrame</code> 
property.


## Parameters

|Name|Description|
|:---|:---|
|`KeyCode` key|The  <code>UnityEngine.KeyCode</code>  to check for the state of.|

## Returns

Whether the key was pressed this frame.

