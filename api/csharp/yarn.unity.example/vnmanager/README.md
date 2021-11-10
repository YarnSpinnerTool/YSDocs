# VNManager

runs Yarn commands and manages sprites for the Visual Novel example

```csharp
public class VNManager : MonoBehaviour, MonoBehaviour
```

## Fields

| Name                                      | Description |
| ----------------------------------------- | ----------- |
| [`actors`](broken-reference)              |             |
| [`actors`](broken-reference)              |             |
| [`bgImage`](broken-reference)             |             |
| [`bgImage`](broken-reference)             |             |
| [`defaultTint`](broken-reference)         |             |
| [`defaultTint`](broken-reference)         |             |
| [`fadeBG`](broken-reference)              |             |
| [`fadeBG`](broken-reference)              |             |
| [`genericAudioSource`](broken-reference)  |             |
| [`genericAudioSource`](broken-reference)  |             |
| [`genericSprite`](broken-reference)       |             |
| [`genericSprite`](broken-reference)       |             |
| [`highlightTint`](broken-reference)       |             |
| [`highlightTint`](broken-reference)       |             |
| [`loadAudio`](broken-reference)           |             |
| [`loadAudio`](broken-reference)           |             |
| [`loadSprites`](broken-reference)         |             |
| [`loadSprites`](broken-reference)         |             |
| [`nameplateBG`](broken-reference)         |             |
| [`nameplateBG`](broken-reference)         |             |
| [`spriteGroup`](broken-reference)         |             |
| [`spriteGroup`](broken-reference)         |             |
| [`useResourcesFolders`](broken-reference) |             |
| [`useResourcesFolders`](broken-reference) |             |

## Methods

| Name                                                                   | Description                                                                                                                                                                                                                                                                      |
| ---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`DoSceneChange(String)`](broken-reference)                            | changes background image                                                                                                                                                                                                                                                         |
| [`DoSceneChange(String)`](broken-reference)                            | changes background image                                                                                                                                                                                                                                                         |
| [`FlipSprite(String, String)`](broken-reference)                       |                                                                                                                                                                                                                                                                                  |
| [`FlipSprite(String, String)`](broken-reference)                       |                                                                                                                                                                                                                                                                                  |
| [`HideAllSprites()`](broken-reference)                                 | HideAll doesn't actually use any parameters                                                                                                                                                                                                                                      |
| [`HideAllSprites()`](broken-reference)                                 | HideAll doesn't actually use any parameters                                                                                                                                                                                                                                      |
| [`HideSprite(String)`](broken-reference)                               | Hide(spriteName). "spriteName" can use wildcards, e.g. HideSprite(Sally\*) will hide both SallyIdle and Sally\_Happy                                                                                                                                                             |
| [`HideSprite(String)`](broken-reference)                               | Hide(spriteName). "spriteName" can use wildcards, e.g. HideSprite(Sally\*) will hide both SallyIdle and Sally\_Happy                                                                                                                                                             |
| [`HighlightSprite(Image)`](broken-reference)                           |                                                                                                                                                                                                                                                                                  |
| [`HighlightSprite(Image)`](broken-reference)                           |                                                                                                                                                                                                                                                                                  |
| [`MoveSprite(String, String, String, Single)`](broken-reference)       |                                                                                                                                                                                                                                                                                  |
| [`MoveSprite(String, String, String, Single)`](broken-reference)       |                                                                                                                                                                                                                                                                                  |
| [`OnActorSpeak(String)`](broken-reference)                             |                                                                                                                                                                                                                                                                                  |
| [`OnActorSpeak(String)`](broken-reference)                             |                                                                                                                                                                                                                                                                                  |
| [`PlayAudio(String, Single, String)`](broken-reference)                | PlayAudio( soundName,volume,"loop" )... PlayAudio(soundName,1.0) plays soundName once at 100% volume... if third parameter was word "loop" it would loop "volume" is a number from 0.0 to 1.0 "loop" is the word "loop" (or "true"), which tells the sound to loop over and over |
| [`PlayAudio(String, Single, String)`](broken-reference)                | PlayAudio( soundName,volume,"loop" )... PlayAudio(soundName,1.0) plays soundName once at 100% volume... if third parameter was word "loop" it would loop "volume" is a number from 0.0 to 1.0 "loop" is the word "loop" (or "true"), which tells the sound to loop over and over |
| [`ResetScene()`](broken-reference)                                     | Reset doesn't actually use any parameters                                                                                                                                                                                                                                        |
| [`ResetScene()`](broken-reference)                                     | Reset doesn't actually use any parameters                                                                                                                                                                                                                                        |
| [`SetActor(String, String, String, String, String)`](broken-reference) | SetActor(actorName,spriteName,positionX,positionY,color) main function for moving / adjusting characters                                                                                                                                                                         |
| [`SetActor(String, String, String, String, String)`](broken-reference) | SetActor(actorName,spriteName,positionX,positionY,color) main function for moving / adjusting characters                                                                                                                                                                         |
| [`SetCameraOffset(String, String, Single)`](broken-reference)          | pan the camera. Usage: CameraOffset(xPos, yPos, moveTime)                                                                                                                                                                                                                        |
| [`SetCameraOffset(String, String, Single)`](broken-reference)          | pan the camera. Usage: CameraOffset(xPos, yPos, moveTime)                                                                                                                                                                                                                        |
| [`SetFade(String, Single, Single, Single)`](broken-reference)          | typical screen fade effect, good for transitions? usage: Fade( #hexcolor, startAlpha, endAlpha, fadeTime )                                                                                                                                                                       |
| [`SetFade(String, Single, Single, Single)`](broken-reference)          | typical screen fade effect, good for transitions? usage: Fade( #hexcolor, startAlpha, endAlpha, fadeTime )                                                                                                                                                                       |
| [`SetFadeIn(Single)`](broken-reference)                                | convenient for an easy fade in, no matter what the previous fade color or alpha was                                                                                                                                                                                              |
| [`SetFadeIn(Single)`](broken-reference)                                | convenient for an easy fade in, no matter what the previous fade color or alpha was                                                                                                                                                                                              |
| [`SetSpriteUnity(String, String, String)`](broken-reference)           |                                                                                                                                                                                                                                                                                  |
| [`SetSpriteUnity(String, String, String)`](broken-reference)           |                                                                                                                                                                                                                                                                                  |
| [`SetSpriteYarn(String, String, String)`](broken-reference)            | Draw(spriteName,positionX,positionY) generic function for sprite drawing                                                                                                                                                                                                         |
| [`SetSpriteYarn(String, String, String)`](broken-reference)            | Draw(spriteName,positionX,positionY) generic function for sprite drawing                                                                                                                                                                                                         |
| [`ShakeSprite(String, Single)`](broken-reference)                      | Shake(actorName or spriteName, strength=0.5)                                                                                                                                                                                                                                     |
| [`ShakeSprite(String, Single)`](broken-reference)                      | Shake(actorName or spriteName, strength=0.5)                                                                                                                                                                                                                                     |
| [`StopAudio(String)`](broken-reference)                                | stops sound playback based on sound name, whether it's looping or not                                                                                                                                                                                                            |
| [`StopAudio(String)`](broken-reference)                                | stops sound playback based on sound name, whether it's looping or not                                                                                                                                                                                                            |
| [`StopAudioAll()`](broken-reference)                                   | stops all currently playing sounds, doesn't actually take any parameters                                                                                                                                                                                                         |
| [`StopAudioAll()`](broken-reference)                                   | stops all currently playing sounds, doesn't actually take any parameters                                                                                                                                                                                                         |

## Namespace

[`Yarn.Unity.Example`](../)

## Assembly

YarnSpinner.dll

## Source

Defined in [../YarnSpinner-Unity-Dev/Packages/YarnSpinner/Samples\~/VisualNovel/Scripts/VNManager.cs](https://github.com/YarnSpinnerTool/YarnSpinner-Unity/blob/develop/Samples\~/VisualNovel/Scripts/VNManager.cs#L11), line 11.
