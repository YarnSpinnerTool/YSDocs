# VNManager

runs Yarn commands and manages sprites for the Visual Novel example

```csharp
public class VNManager : MonoBehaviour, MonoBehaviour
```

## Fields

| Name | Description |
| :--- | :--- |
| [`actors`]() |  |
| [`actors`]() |  |
| [`bgImage`]() |  |
| [`bgImage`]() |  |
| [`defaultTint`]() |  |
| [`defaultTint`]() |  |
| [`fadeBG`]() |  |
| [`fadeBG`]() |  |
| [`genericAudioSource`]() |  |
| [`genericAudioSource`]() |  |
| [`genericSprite`]() |  |
| [`genericSprite`]() |  |
| [`highlightTint`]() |  |
| [`highlightTint`]() |  |
| [`loadAudio`]() |  |
| [`loadAudio`]() |  |
| [`loadSprites`]() |  |
| [`loadSprites`]() |  |
| [`nameplateBG`]() |  |
| [`nameplateBG`]() |  |
| [`spriteGroup`]() |  |
| [`spriteGroup`]() |  |
| [`useResourcesFolders`]() |  |
| [`useResourcesFolders`]() |  |

## Methods

| Name | Description |
| :--- | :--- |
| [`DoSceneChange(String)`]() | changes background image |
| [`DoSceneChange(String)`]() | changes background image |
| [`FlipSprite(String, String)`]() |  |
| [`FlipSprite(String, String)`]() |  |
| [`HideAllSprites()`]() | HideAll doesn't actually use any parameters |
| [`HideAllSprites()`]() | HideAll doesn't actually use any parameters |
| [`HideSprite(String)`]() | Hide\(spriteName\). "spriteName" can use wildcards, e.g. HideSprite\(Sally\*\) will hide both SallyIdle and Sally\_Happy |
| [`HideSprite(String)`]() | Hide\(spriteName\). "spriteName" can use wildcards, e.g. HideSprite\(Sally\*\) will hide both SallyIdle and Sally\_Happy |
| [`HighlightSprite(Image)`]() |  |
| [`HighlightSprite(Image)`]() |  |
| [`MoveSprite(String, String, String, Single)`]() |  |
| [`MoveSprite(String, String, String, Single)`]() |  |
| [`OnActorSpeak(String)`]() |  |
| [`OnActorSpeak(String)`]() |  |
| [`PlayAudio(String, Single, String)`]() | PlayAudio\( soundName,volume,"loop" \)... PlayAudio\(soundName,1.0\) plays soundName once at 100% volume... if third parameter was word "loop" it would loop "volume" is a number from 0.0 to 1.0 "loop" is the word "loop" \(or "true"\), which tells the sound to loop over and over |
| [`PlayAudio(String, Single, String)`]() | PlayAudio\( soundName,volume,"loop" \)... PlayAudio\(soundName,1.0\) plays soundName once at 100% volume... if third parameter was word "loop" it would loop "volume" is a number from 0.0 to 1.0 "loop" is the word "loop" \(or "true"\), which tells the sound to loop over and over |
| [`ResetScene()`]() | Reset doesn't actually use any parameters |
| [`ResetScene()`]() | Reset doesn't actually use any parameters |
| [`SetActor(String, String, String, String, String)`]() | SetActor\(actorName,spriteName,positionX,positionY,color\) main function for moving / adjusting characters |
| [`SetActor(String, String, String, String, String)`]() | SetActor\(actorName,spriteName,positionX,positionY,color\) main function for moving / adjusting characters |
| [`SetCameraOffset(String, String, Single)`]() | pan the camera. Usage: CameraOffset\(xPos, yPos, moveTime\) |
| [`SetCameraOffset(String, String, Single)`]() | pan the camera. Usage: CameraOffset\(xPos, yPos, moveTime\) |
| [`SetFade(String, Single, Single, Single)`]() | typical screen fade effect, good for transitions? usage: Fade\( \#hexcolor, startAlpha, endAlpha, fadeTime \) |
| [`SetFade(String, Single, Single, Single)`]() | typical screen fade effect, good for transitions? usage: Fade\( \#hexcolor, startAlpha, endAlpha, fadeTime \) |
| [`SetFadeIn(Single)`]() | convenient for an easy fade in, no matter what the previous fade color or alpha was |
| [`SetFadeIn(Single)`]() | convenient for an easy fade in, no matter what the previous fade color or alpha was |
| [`SetSpriteUnity(String, String, String)`]() |  |
| [`SetSpriteUnity(String, String, String)`]() |  |
| [`SetSpriteYarn(String, String, String)`]() | Draw\(spriteName,positionX,positionY\) generic function for sprite drawing |
| [`SetSpriteYarn(String, String, String)`]() | Draw\(spriteName,positionX,positionY\) generic function for sprite drawing |
| [`ShakeSprite(String, Single)`]() | Shake\(actorName or spriteName, strength=0.5\) |
| [`ShakeSprite(String, Single)`]() | Shake\(actorName or spriteName, strength=0.5\) |
| [`StopAudio(String)`]() | stops sound playback based on sound name, whether it's looping or not |
| [`StopAudio(String)`]() | stops sound playback based on sound name, whether it's looping or not |
| [`StopAudioAll()`]() | stops all currently playing sounds, doesn't actually take any parameters |
| [`StopAudioAll()`]() | stops all currently playing sounds, doesn't actually take any parameters |

## Namespace

[`Yarn.Unity.Example`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Samples~/VisualNovel/Scripts/VNManager.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity//blob/develop/Samples~/VisualNovel/Scripts/VNManager.cs#L11), line 11.

