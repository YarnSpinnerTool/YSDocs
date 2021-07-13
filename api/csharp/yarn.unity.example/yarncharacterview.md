# YarnCharacterView Class
Manager singleton that repositions DialogueUI window in 3D worldspace, based on whoever is speaking. Put this script on the same gameObject as your DialogueUI.

```csharp
public class YarnCharacterView : DialogueViewBase
```



## Fields
|Name|Description|
|:---|:---|
|[allCharacters](/api/csharp/yarn.unity.example/yarncharacterview.allcharacters.md)||
|[allCharacters](/api/csharp/yarn.unity.example/yarncharacterview.allcharacters.md)||
|[bubbleMargin](/api/csharp/yarn.unity.example/yarncharacterview.bubblemargin.md)||
|[bubbleMargin](/api/csharp/yarn.unity.example/yarncharacterview.bubblemargin.md)||
|[canvas](/api/csharp/yarn.unity.example/yarncharacterview.canvas.md)||
|[canvas](/api/csharp/yarn.unity.example/yarncharacterview.canvas.md)||
|[canvasScaler](/api/csharp/yarn.unity.example/yarncharacterview.canvasscaler.md)||
|[canvasScaler](/api/csharp/yarn.unity.example/yarncharacterview.canvasscaler.md)||
|[dialogueBubbleRect](/api/csharp/yarn.unity.example/yarncharacterview.dialoguebubblerect.md)||
|[dialogueBubbleRect](/api/csharp/yarn.unity.example/yarncharacterview.dialoguebubblerect.md)||
|[instance](/api/csharp/yarn.unity.example/yarncharacterview.instance.md)||
|[instance](/api/csharp/yarn.unity.example/yarncharacterview.instance.md)||
|[optionsBubbleRect](/api/csharp/yarn.unity.example/yarncharacterview.optionsbubblerect.md)||
|[optionsBubbleRect](/api/csharp/yarn.unity.example/yarncharacterview.optionsbubblerect.md)||
|[playerCharacter](/api/csharp/yarn.unity.example/yarncharacterview.playercharacter.md)||
|[playerCharacter](/api/csharp/yarn.unity.example/yarncharacterview.playercharacter.md)||
## Methods
|Name|Description|
|:---|:---|
|[DismissLine(Action)](/api/csharp/yarn.unity.example/yarncharacterview.dismissline-action-.md)||
|[DismissLine(Action)](/api/csharp/yarn.unity.example/yarncharacterview.dismissline-action-.md)||
|[ForgetYarnCharacter(YarnCharacter)](/api/csharp/yarn.unity.example/yarncharacterview.forgetyarncharacter-yarncharacter-.md)|automatically called by YarnCharacter.OnDestroy() to clean-up|
|[ForgetYarnCharacter(YarnCharacter)](/api/csharp/yarn.unity.example/yarncharacterview.forgetyarncharacter-yarncharacter-.md)|automatically called by YarnCharacter.OnDestroy() to clean-up|
|[OnLineStatusChanged(LocalizedLine)](/api/csharp/yarn.unity.example/yarncharacterview.onlinestatuschanged-yarn.unity.localizedline-.md)||
|[OnLineStatusChanged(LocalizedLine)](/api/csharp/yarn.unity.example/yarncharacterview.onlinestatuschanged-yarn.unity.localizedline-.md)||
|[RegisterYarnCharacter(YarnCharacter)](/api/csharp/yarn.unity.example/yarncharacterview.registeryarncharacter-yarncharacter-.md)|automatically called by YarnCharacter.Start() so that YarnCharacterView knows they exist|
|[RegisterYarnCharacter(YarnCharacter)](/api/csharp/yarn.unity.example/yarncharacterview.registeryarncharacter-yarncharacter-.md)|automatically called by YarnCharacter.Start() so that YarnCharacterView knows they exist|
|[RunLine(LocalizedLine, Action)](/api/csharp/yarn.unity.example/yarncharacterview.runline-yarn.unity.localizedline,action-.md)||
|[RunLine(LocalizedLine, Action)](/api/csharp/yarn.unity.example/yarncharacterview.runline-yarn.unity.localizedline,action-.md)||
|[RunOptions(DialogueOption[], Action<Int32>)](/api/csharp/yarn.unity.example/yarncharacterview.runoptions-yarn.unity.dialogueoption--,action-system.int32--.md)||
|[RunOptions(DialogueOption[], Action<Int32>)](/api/csharp/yarn.unity.example/yarncharacterview.runoptions-yarn.unity.dialogueoption--,action-system.int32--.md)||
<div class="class-metadata">

Namespace: [`Yarn.Unity.Example`](/api/csharp/yarn.unity.example/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Samples~/3D/Scripts/YarnCharacterView.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Samples~/3D/Scripts/YarnCharacterView.cs#L10), line 10.
