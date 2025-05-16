---
description: Learn how to trigger events using markup, inline with your dialogue.
---

# Inline Events

Yarn Spinner version 3 introduces a powerful new way to trigger events during dialogue presentation. While previous versions required custom implementations for in-line actions, v3 provides the `IActionMarkupHandler` interface. This system notifies handlers about key line presentation events, enabling you to respond at specific moments.

This approach offers tremendous flexibility for creating various inline events. Our sample demonstrates two practical applications: character movement and facial expression changes during dialogue presentation.

This guide explores the contents of the **Inline Events** Sample.

{% include "../../.gitbook/includes/you-can-learn-how-to-add-th....md" %}

{% embed url="https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F1BtiYLyfkkFBrMlsYGWS%2Fuploads%2FWi0jtDAgWMWIflmp3E31%2Fopening.mp4?alt=media&token=d5af8ce7-f952-4c51-b7e2-17d84b921b38" %}

### What we'll be covering

* The new `IActionMarkupHandler` interface
* The new `ActionMarkupHandler` class
* Using these with the Line Presenter to trigger events
* Two implementations: character movement and animation changes

### The Action Markup Handler

The `IActionMarkupHandler` interface provides a structured approach to handling in-line actions during dialogue presentation. At its core, the system works by having the Line Presenter display dialogue one character at a time, notifying handlers throughout the process. This creates multiple opportunities to trigger events at precise moments.

The interface defines methods corresponding to different stages of the line presentation lifecycle:

1. **Initial Preparation** (`OnPrepareForLine`): Called immediately after the line is received but before any UI elements appear.
2. **Display Start** (`OnLineDisplayBegin`): Called just before characters begin appearing, but after UI elements are visible.
3. **Character Display** (`OnCharacterWillAppear`): Called each time a character in the line is about to be displayed.
4. **Display Completion** (`OnLineDisplayComplete`): Called after all characters in the line have been shown.
5. **Dismissal** (`OnLineWillDismiss`): Called just before the line will be dismissed.

Notably, `OnCharacterWillAppear` is an asynchronous method. The line presentation system will await each Action Markup Handler's completion before continuing, allowing events of any duration to occur at any point in the dialogue.

Yarn Spinner also provides `ActionMarkupHandler`, a MonoBehaviour implementation of this interface, for situations where you need component-based functionality. The Line Presenter includes a serialized field for directly connecting `ActionMarkupHandler` subclasses, as demonstrated in our sample.

### The Sample

Our sample showcases two types of action markup: moving the player character and changing NPC facial expressions. Both are implemented as `ActionMarkupHandler` subclasses and connected to the Line Presenter through its `Event Processors` field.

#### Movement

The movement implementation resides in the `MoveEvent.cs` file as an `ActionMarkupHandler` subclass. Most of the functionality is contained in the `OnPrepareForLine` method.

This method scans all markup in the current line, searching specifically for the `move` markup tag. When found, it extracts the `name` property from the marker and uses it to locate a corresponding in-scene marker with the same name. The target location and the marker position within the text are stored in a dictionary for later use.

During line presentation, the `OnCharacterWillAppear` method checks if the current character position corresponds to a stored location. If so, it moves the player character to that position before continuing.

This allows for dialogue lines such as: `Player: So what, just part way through I stop talking... [move name="far" /] ...and move on over?`

When presentation reaches position 49, it will pause, the player character will move to the GameObject named "far", and then the dialogue will resume.

#### Emotion

The facial expression system is implemented in `EmotionEvent.cs` as another `ActionMarkupHandler` subclass. The primary logic is also in the `OnPrepareForLine` method.

This implementation first uses the character name from the dialogue line to find a corresponding GameObject. It then retrieves the `SimpleCharacter` component (a sample-specific type, not part of Yarn Spinner core) from this GameObject. After these preparations, it processes all markup in the line, looking specifically for `emotion` tags. The `emotion` property value is extracted and stored for later use.

During presentation, `OnCharacterWillAppear` checks if there's a cached emotion corresponding to the current position. If found, it uses this value to change the character's facial expression animation. Unlike the movement example, this change happens instantly without pausing dialogue progression.

This enables dialogue lines like: `Alice: Yes... which I would have shown [emotion="angry" /] had you not interrupted me.`

When presentation reaches position 32, the facial expression of the "Alice" GameObject will instantly change to whatever animation corresponds to "angry" while the dialogue continues uninterrupted.
