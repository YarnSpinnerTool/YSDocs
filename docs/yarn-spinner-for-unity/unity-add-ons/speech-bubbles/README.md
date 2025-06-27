---
description: >-
  The guide and documentation for the paid Yarn Spinner for Unity add-on, Speech
  Bubbles for Yarn Spinner.
icon: comments
---

# Speech Bubbles

<figure><img src="../../../.gitbook/assets/Speech Bubbles - Banner.png" alt=""><figcaption></figcaption></figure>

This Unity package provides two prefabs: **Formal Bubble** and **Casual Bubble**. The package requires Yarn Spinner for Unity.

This add-on is not part of the open source Yarn Spinner package, and can be [purchased from the Yarn Spinner Itch.io Store](https://yarnspinner.itch.io/speech-bubbles-for-yarn-spinner) or via the [Unity Asset Store](https://assetstore.unity.com/packages/tools/gui/speech-bubbles-for-yarn-spinner-275933).

{% embed url="https://yarnspinner.itch.io/speech-bubbles-for-yarn-spinner" %}

{% embed url="https://assetstore.unity.com/packages/tools/gui/speech-bubbles-for-yarn-spinner-275933" %}

Speech Bubbles for Yarn Spinner provides a **Casual Bubble** and a **Formal Bubble** prefab. Both are customisable, powerful, and extremely flexible:

* customise fonts, colours, and styles of bubbles
* optional character nameplate
* flexible anchor point for bubble stem
* lock bubbles to camera, or not, your choice
* works for 2D or 3D games

This guide provides documentation on using the bubbles and both prefabs.

{% hint style="danger" %}
The oldest supported version of Unity for the Speech Bubbles is 2022.3.
{% endhint %}

## Speech Bubble Architecture

The design of the Speech Bubbles are slightly different to how most custom dialogue presenters, or even the default presenters, work. At first glance it might not be obvious as to what each piece does, that is what this section is for.

### Bubble Dialogue View

The Bubble Dialogue View is the [presenter](../../components/dialogue-view/) subclass and is what talks to the [Dialogue Runner](../../components/dialogue-runner.md) for the relevant events in the story. The Bubble Dialogue View manages all the various bubbles that will need to be shown on screen, in particular it controls when to create and destroy them and gives them the content they need to show. The Bubble Dialogue View is a essentially a middle-man between the actual game objects shown on screen and Yarn Spinner.

### Bubbles and Bubble Content

The Bubble and Bubble Content are the two classes that control where and what is shown on the screen. The Bubble manages positioning information, determining where to best place the canvas rectangle. What a Bubble appears like, so it's shape, text, colours, and so on are determined by it's Bubble Content.

The Bubble Content represents a single piece of content. So each line that needs to be shown is a piece of content, the collection of options is another piece of content. The Bubble then shows this piece of content, and when a new piece of content comes in removes the old and shows the new. The Bubble gets given this Bubble Content to show by it's Bubble Dialogue View. The specific information contained within a Bubble Content changes depending on what needs to be shown to the player, the most common information is the line.

The reason for this split is because the way a bubble determines where to place itself is not significantly impacted by it's content. Only the size of the text inside the content changes this, the rest is the same no matter what. This means a great deal of code could be extracted and kept generic from the rest of the presentation. This means making visually unique bubbles is now easier by subclassing the Bubble Content, all the positioning code can be reused for every visually different bubble.

### Bubble Input

The last class that operates in a different manner from the Yarn Spinner norm is the Bubble Input. When the user wants to hurry up or skip lines in Yarn Spinner this is handled by the [Line Advancer](../../components/dialogue-view/line-presenter.md), Speech Bubbles however are a bit different in this respect. Because they can only show a single option at a time they need to have a way to also support changing between which option is currently being shown by the bubble, this is what the Bubble Input does.

The Line Advancer is still a part of the equation, as hurrying up lines is still something people will want to do with Speech Bubbles, however it is no longer directly configured by you in the editor. Instead Bubble Input has a reference to the Line Advancer and it will set the appropriate values. This is just to avoid having to change two objects at once, however if you do want to have this behaviour the Bubble Input has a toggle called `Independent Advancer Configuration` where if set means the Bubble Input won't attempt to change the configuration of the Line Advancer.

{% hint style="info" %}
tldr you set the values for hurrying up, skipping, and cancelling lines on the Bubble Input.
{% endhint %}
