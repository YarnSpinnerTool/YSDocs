# VNManager Class

runs Yarn commands and manages sprites for the Visual Novel example


```csharp
public class VNManager : MonoBehaviour, MonoBehaviour
```



## Fields
|Name|Description|
|:---|:---|
|[actors](/api/csharp/yarn.unity.example/vnmanager.actors.md)||
|[actors](/api/csharp/yarn.unity.example/vnmanager.actors.md)||
|[bgImage](/api/csharp/yarn.unity.example/vnmanager.bgimage.md)||
|[bgImage](/api/csharp/yarn.unity.example/vnmanager.bgimage.md)||
|[defaultTint](/api/csharp/yarn.unity.example/vnmanager.defaulttint.md)||
|[defaultTint](/api/csharp/yarn.unity.example/vnmanager.defaulttint.md)||
|[fadeBG](/api/csharp/yarn.unity.example/vnmanager.fadebg.md)||
|[fadeBG](/api/csharp/yarn.unity.example/vnmanager.fadebg.md)||
|[genericAudioSource](/api/csharp/yarn.unity.example/vnmanager.genericaudiosource.md)||
|[genericAudioSource](/api/csharp/yarn.unity.example/vnmanager.genericaudiosource.md)||
|[genericSprite](/api/csharp/yarn.unity.example/vnmanager.genericsprite.md)||
|[genericSprite](/api/csharp/yarn.unity.example/vnmanager.genericsprite.md)||
|[highlightTint](/api/csharp/yarn.unity.example/vnmanager.highlighttint.md)||
|[highlightTint](/api/csharp/yarn.unity.example/vnmanager.highlighttint.md)||
|[loadAudio](/api/csharp/yarn.unity.example/vnmanager.loadaudio.md)||
|[loadAudio](/api/csharp/yarn.unity.example/vnmanager.loadaudio.md)||
|[loadSprites](/api/csharp/yarn.unity.example/vnmanager.loadsprites.md)||
|[loadSprites](/api/csharp/yarn.unity.example/vnmanager.loadsprites.md)||
|[nameplateBG](/api/csharp/yarn.unity.example/vnmanager.nameplatebg.md)||
|[nameplateBG](/api/csharp/yarn.unity.example/vnmanager.nameplatebg.md)||
|[spriteGroup](/api/csharp/yarn.unity.example/vnmanager.spritegroup.md)||
|[spriteGroup](/api/csharp/yarn.unity.example/vnmanager.spritegroup.md)||
|[useResourcesFolders](/api/csharp/yarn.unity.example/vnmanager.useresourcesfolders.md)||
|[useResourcesFolders](/api/csharp/yarn.unity.example/vnmanager.useresourcesfolders.md)||
## Methods
|Name|Description|
|:---|:---|
|[DoSceneChange(String)](/api/csharp/yarn.unity.example/vnmanager.doscenechange-system.string-.md)|changes background image|
|[DoSceneChange(String)](/api/csharp/yarn.unity.example/vnmanager.doscenechange-system.string-.md)|changes background image|
|[FlipSprite(String, String)](/api/csharp/yarn.unity.example/vnmanager.flipsprite-system.string,system.string-.md)||
|[FlipSprite(String, String)](/api/csharp/yarn.unity.example/vnmanager.flipsprite-system.string,system.string-.md)||
|[HideAllSprites()](/api/csharp/yarn.unity.example/vnmanager.hideallsprites.md)|HideAll doesn't actually use any parameters|
|[HideAllSprites()](/api/csharp/yarn.unity.example/vnmanager.hideallsprites.md)|HideAll doesn't actually use any parameters|
|[HideSprite(String)](/api/csharp/yarn.unity.example/vnmanager.hidesprite-system.string-.md)|Hide(spriteName). "spriteName" can use wildcards, e.g. HideSprite(Sally*) will hide both SallyIdle and Sally_Happy|
|[HideSprite(String)](/api/csharp/yarn.unity.example/vnmanager.hidesprite-system.string-.md)|Hide(spriteName). "spriteName" can use wildcards, e.g. HideSprite(Sally*) will hide both SallyIdle and Sally_Happy|
|[HighlightSprite(Image)](/api/csharp/yarn.unity.example/vnmanager.highlightsprite-image-.md)||
|[HighlightSprite(Image)](/api/csharp/yarn.unity.example/vnmanager.highlightsprite-image-.md)||
|[MoveSprite(String, String, String, Single)](/api/csharp/yarn.unity.example/vnmanager.movesprite-system.string,system.string,system.string,system.single-.md)||
|[MoveSprite(String, String, String, Single)](/api/csharp/yarn.unity.example/vnmanager.movesprite-system.string,system.string,system.string,system.single-.md)||
|[OnActorSpeak(String)](/api/csharp/yarn.unity.example/vnmanager.onactorspeak-system.string-.md)||
|[OnActorSpeak(String)](/api/csharp/yarn.unity.example/vnmanager.onactorspeak-system.string-.md)||
|[PlayAudio(String, Single, String)](/api/csharp/yarn.unity.example/vnmanager.playaudio-system.string,system.single,system.string-.md)|PlayAudio( soundName,volume,"loop" )... PlayAudio(soundName,1.0) plays soundName once at 100% volume... if third parameter was word "loop" it would loop "volume" is a number from 0.0 to 1.0 "loop" is the word "loop" (or "true"), which tells the sound to loop over and over|
|[PlayAudio(String, Single, String)](/api/csharp/yarn.unity.example/vnmanager.playaudio-system.string,system.single,system.string-.md)|PlayAudio( soundName,volume,"loop" )... PlayAudio(soundName,1.0) plays soundName once at 100% volume... if third parameter was word "loop" it would loop "volume" is a number from 0.0 to 1.0 "loop" is the word "loop" (or "true"), which tells the sound to loop over and over|
|[ResetScene()](/api/csharp/yarn.unity.example/vnmanager.resetscene.md)|Reset doesn't actually use any parameters|
|[ResetScene()](/api/csharp/yarn.unity.example/vnmanager.resetscene.md)|Reset doesn't actually use any parameters|
|[SetActor(String, String, String, String, String)](/api/csharp/yarn.unity.example/vnmanager.setactor-system.string,system.string,system.string,system.string,system.string-.md)| SetActor(actorName,spriteName,positionX,positionY,color) main function for moving / adjusting characters|
|[SetActor(String, String, String, String, String)](/api/csharp/yarn.unity.example/vnmanager.setactor-system.string,system.string,system.string,system.string,system.string-.md)| SetActor(actorName,spriteName,positionX,positionY,color) main function for moving / adjusting characters|
|[SetCameraOffset(String, String, Single)](/api/csharp/yarn.unity.example/vnmanager.setcameraoffset-system.string,system.string,system.single-.md)|pan the camera. Usage: CameraOffset(xPos, yPos, moveTime)|
|[SetCameraOffset(String, String, Single)](/api/csharp/yarn.unity.example/vnmanager.setcameraoffset-system.string,system.string,system.single-.md)|pan the camera. Usage: CameraOffset(xPos, yPos, moveTime)|
|[SetFade(String, Single, Single, Single)](/api/csharp/yarn.unity.example/vnmanager.setfade-system.string,system.single,system.single,system.single-.md)|typical screen fade effect, good for transitions? usage: Fade( #hexcolor, startAlpha, endAlpha, fadeTime )|
|[SetFade(String, Single, Single, Single)](/api/csharp/yarn.unity.example/vnmanager.setfade-system.string,system.single,system.single,system.single-.md)|typical screen fade effect, good for transitions? usage: Fade( #hexcolor, startAlpha, endAlpha, fadeTime )|
|[SetFadeIn(Single)](/api/csharp/yarn.unity.example/vnmanager.setfadein-system.single-.md)|convenient for an easy fade in, no matter what the previous fade color or alpha was|
|[SetFadeIn(Single)](/api/csharp/yarn.unity.example/vnmanager.setfadein-system.single-.md)|convenient for an easy fade in, no matter what the previous fade color or alpha was|
|[SetSpriteUnity(String, String, String)](/api/csharp/yarn.unity.example/vnmanager.setspriteunity-system.string,system.string,system.string-.md)||
|[SetSpriteUnity(String, String, String)](/api/csharp/yarn.unity.example/vnmanager.setspriteunity-system.string,system.string,system.string-.md)||
|[SetSpriteYarn(String, String, String)](/api/csharp/yarn.unity.example/vnmanager.setspriteyarn-system.string,system.string,system.string-.md)|Draw(spriteName,positionX,positionY) generic function for sprite drawing|
|[SetSpriteYarn(String, String, String)](/api/csharp/yarn.unity.example/vnmanager.setspriteyarn-system.string,system.string,system.string-.md)|Draw(spriteName,positionX,positionY) generic function for sprite drawing|
|[ShakeSprite(String, Single)](/api/csharp/yarn.unity.example/vnmanager.shakesprite-system.string,system.single-.md)|Shake(actorName or spriteName, strength=0.5)|
|[ShakeSprite(String, Single)](/api/csharp/yarn.unity.example/vnmanager.shakesprite-system.string,system.single-.md)|Shake(actorName or spriteName, strength=0.5)|
|[StopAudio(String)](/api/csharp/yarn.unity.example/vnmanager.stopaudio-system.string-.md)|stops sound playback based on sound name, whether it's looping or not|
|[StopAudio(String)](/api/csharp/yarn.unity.example/vnmanager.stopaudio-system.string-.md)|stops sound playback based on sound name, whether it's looping or not|
|[StopAudioAll()](/api/csharp/yarn.unity.example/vnmanager.stopaudioall.md)|stops all currently playing sounds, doesn't actually take any parameters|
|[StopAudioAll()](/api/csharp/yarn.unity.example/vnmanager.stopaudioall.md)|stops all currently playing sounds, doesn't actually take any parameters|
<div class="class-metadata">

Namespace: [`Yarn.Unity.Example`](/api/csharp/yarn.unity.example/README.md), Assembly: YarnSpinner.dll
</div>

## Source
Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Samples~/VisualNovel/Scripts/VNManager.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Samples~/VisualNovel/Scripts/VNManager.cs#L11), line 11.
