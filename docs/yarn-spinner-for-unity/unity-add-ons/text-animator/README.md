---
description: Learn about Text Animator for Yarn Spinner.
icon: font
---

# Text Animator

## A Yarn Spinner for Unity typewriter, for better integration with Text Animator for Unity.

That's a lot of "for Unity"s. Welcome to the official Yarn Spinner integration for [Text Animator](https://www.textanimatorforgames.com), the best package out there for animated text in Unity (and other engines, too!)

Text Animator for Yarn Spinner seamlessly integrates Text Animator with your Yarn Spinner dialogue presenters. All you need to do is add a Text Animator component to your text view, and connect it up to your Dialogue Presenter. Once that's done, you can use Text Animator animations alongside your Yarn Spinner markup!

Text Animator for Yarn Spinner supports Text Animator versions 2 and 3. We recommend Text Animator 3 - it's got more features, and the integration is easier!

## Getting Text Animator for Yarn Spinner

Text Animator for Yarn Spinner is included in the paid [itch.io](https://yarnspinner.itch.io/yarn-spinner) and [Unity Asset Store](https://assetstore.unity.com/packages/tools/behavior-ai/yarn-spinner-for-unity-the-friendly-dialogue-and-narrative-tool-267061) and versions of Yarn Spinner.

## Getting started

To get started with Text Animator for Unity, you'll need to install the following components:

* Yarn Spinner for Unity 3.1 from the [Unity Asset Store](https://assetstore.unity.com/packages/tools/behavior-ai/yarn-spinner-for-unity-the-friendly-dialogue-and-narrative-tool-267061) or [itch.io](https://yarnspinner.itch.io/yarn-spinner)
* [Text Animator for Unity](https://www.textanimatorforgames.com/unity)

Once these are installed, open the config window (Window -> Yarn Spinner -> Text Animator Config). It will guide you through setting up the integration.

### Using Text Animator Animations

When the setup is complete, you can create a new [Dialogue System](https://docs.yarnspinner.dev/components/dialogue-runner) that's set up to use Text Animator. To do this, open the GameObject menu, and choose Yarn Spinner -> Dialogue System with Text Animator.

This dialogue runner prefab comes with a version of Yarn Spinner's built-in [Line Presenter](https://docs.yarnspinner.dev/components/dialogue-view/line-presenter) that's set up to use Text Animator's typewriter system. To use Text Animator animations, you just use markup. The only difference is that you'll use Yarn Spinner's `[square brackets]` instead of Text Animator's `<angled brackets>`.

For example, try creating a Yarn Spinner script that contains the following line:

```
Text Animator for Yarn Spinner has got me feeling [shake]goosebumps[/shake]!
```

### Integrating Into A Custom Dialogue Presenter

The easiest way to use Text Animator for Yarn Spinner is to take our out-of-the-box view from the previous section and modify it to suit your needs. However, if you've already got custom views that you want to add Text Animator support to, read on!

To make Text Animator's typewriter work with your own custom dialogue presenter, you will need to add Yarn Spinner's "Text Animator Yarn Typewriter" component onto the same object that has your Text Animator component.

Once the Text Animator Yarn Typewriter is added, you can make use of it in your custom dialogue presenter. When your dialogue presenter's `RunLineAsync` method is called, you can send it to the typewriter. Here's an example implementation of `RunLineAsync` that does this:

```csharp
// Connect this to your Text Animator Yarn Typewriter component in the scene
public TextAnimatorYarnTypewriter Typewriter;

public override async YarnTask RunLineAsync(LocalizedLine line, LineCancellationToken token)
{

    // Tell the typewriter that content is going to appear.
    Typewriter.PrepareForContent(line.Text);

    // (At this point, you could fade up your dialogue 
    // UI or perform any other animation needed enter 
    // 'dialogue mode' in your game. In this example, 
    // we'll just proceed right into showing the text.)

    // Show the text. Text Animator for Yarn Spinner 
    // will handle all of the appearance and effects 
    // for you!
    await Typewriter.RunTypewriter(text, token.HurryUpToken).SuppressCancellationThrow();
    
    // Wait until the line has been ended.
    await YarnTask.WaitUntilCanceled(token.NextContentToken).SuppressCancellationThrow();
    
    // Signal that the content is going away.
    Typewriter.ContentWillDismiss();

}
```

## Architecture

Text Animator for Yarn Spinner works by creating a new Yarn Spinner class that conforms to the typewriter interface, which then wraps the various Text Animator components. It can then be hooked up to any presenter the same way as any of the default typewriters (like the 'by word' or 'by letter' typewriter).

The majority of the work happens inside `TextAnimatorYarnTypewriter`, which is a combination typewriter and replacement markup handler. The replacement markup handling is for handling the interplay of Yarn Spinner markup and Text Animator tags.

## Markup and Tags

Both Text Animator and Yarn Spinner have a slightly different philosophy to how their markup and tags should look and work. For the most part we have attempted to make thinking about this a non-issue but our recommended and default way relies on a few things.

The first is we have created a Yarn Spinner replacement markup wrapper for all Text Animator tags and we recommend these be used.

In a practical sense this means a line like:

```
This line has a <rainb>Text Animator effect</rainb> on it.
```

Can also be written as:

```
This line has a [rainb]Text Animator effect[/rainb] on it.
```

With this, the replacement markup system will swap out the right pieces to recreate the first line.

We recommend this approach because, if you are combining Text Animator tags with action markup, we are unable to know that which parts of the text are invisible, and which are not.

For example, given the following line:

```
This line has a <rainb>Text Animator effect</rainb>[pause /] on it.
```

Yarn Spinner doesn't know by itself that the `<rainb>` elements are invisible characters so the position of the `pause` markup will be wrong. To handle this, Text Animator for Yarn Spinner will replace the `<angle bracket>` tags with `[square bracket]` tags, and then handle all of the tags in the same way.

### Shared Tags

In Text Animator, you can share a tag ID across behaviours, actions, and appearances, which isn't possible in Yarn Spinner.

To disambiguate this, you can add a `type` property on the markup attribute. This is used to ensure the correct Text Animator tag is written to the line.

The allowed values for `type` are `behaviour`, `action`, or `appearance`.

This means if you have the following:

```
This line has [custom type="appearance"]tags[/custom] of different [custom type="behaviour"]types[/custom]
```

it will become

```
This line has {custom type="appearance"}tags{/custom} of different <custom type="behaviour">types</custom>
```

Likewise, if you want to add a Text Animator disappearance effect, you set a `disappearance` property to be `true` on the markup. This will correctly add the `#` to the tag as needed.

### Tagging modes in Text Animator 2

{% hint style="info" %}
The following section only applies to Text Animator 2. If you're using Text Animator 3, you don't need to worry about it.
{% endhint %}

When you're using Text Animator 2, there are three modes you can choose between that determine how Yarn Spinner's markup and Text Animator's tags work together.

* Default
* Exclusively Yarn Spinner markup
* Exclusively Text Animator tags

Each of these modes has their own quirks. The **default** mode is what we recommend, as it offers the best blend between features and functionality.

#### Default Mode

You can use replacement markup, action markup, and text animator tags all together in the **default** mode.

This works by inserting a new, custom Text Animator action (which defaults to `<y>`) at each point in the line where any Yarn Spinner action markup is.

For this to work, you need to ensure the name of the action markup is in the `actionTags` property of the Typewriter. (The default one includes the "pause" markup; if you've created your own, you'll need to add them as well.)

As the Text Animator typewrites along the line, it will hit the inserted action. The action will then forward the event over to the appropriate handler.

The downside to this is your action markup handlers will only get told about line progression at these fixed points.

Most of the time this isn't an issue, but if it is, you can run the system in Yarn Spinner Only mode.

### Yarn Spinner Tags Only Mode

Yarn Spinner Tags Only Mode works in a similar manner to default mode: a Text Animator action tag (which defaults to `<y>`) is inserted into the line. However, instead of inserting the tags only at the points of action markup, it is inserted into _every_ single position.

This allows the action markup handlers to receive the full progression of the Typewriter at each point.

The downside is, because of how this works, you can no longer use Text Animator tags in the line, and there is just a lot more string manipulation going on making everything just a bit messier than the default. This mode is best if you need the full action markup event processing.

### Text Animator Tags Only Mode

The final mode is Text Animator Tags Only Mode. In this mode, you can still use replacement Yarn Spinner markup like `[b]` and `[plural]`, but any action markup (or the Yarn Spinner translated forms of Text Animator tags) won't work.

This mode is best if you are already comfortable with Text Animator, and are happy using their tag system exclusively.

This is all summarised via the following table:

|                            | Default | Exclusive Yarn | Exclusive Text Animator |
| -------------------------- | ------- | -------------- | ----------------------- |
| Action Markup              | ✅       | ✅              | ❌                       |
| Replacement Markup         | ✅       | ✅              | ❓                       |
| Wrapped Text Animator Tags | ✅       | ✅              | ❌                       |
| Text Animator Tags         | ❓       | ❌              | ✅                       |

```
✅ = supported and recommended
❓ = supported but not recommended
❌ = not supported
```
