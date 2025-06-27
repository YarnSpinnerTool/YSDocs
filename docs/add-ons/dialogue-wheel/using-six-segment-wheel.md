---
description: >-
  Learn how to use the Image Dialogue Wheel, from the Dialogue Wheel for
  Yarn Spinner Add-On Package.
---

# Using Image Wheel

The Image Dialogue Wheel provides a dialogue wheel with a light sci-fi appearance, and can display up to six responses for your dialogue. You can specify exactly which segment of the wheel each response is located.

## Using the Image Dialogue Wheel

To use the Image Dialogue Wheel [make sure your Unity project has the Yarn Spinner package installed](../../using-yarnspinner-with-unity/installation-and-setup.md), and the [install the Dialogue Wheel for Yarn Spinner package](installing-dialogue-wheel.md).

Then, create a new Dialogue Runner in your Hierarchy:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-23 at 3.30.39 pm.png" alt="" width="563"><figcaption><p>Adding a new Dialogue Runner to your scene.</p></figcaption></figure>

{% hint style="info" %}
If prompted, click the Install TMP Essentials button to install TeshMesh Pro (TMP).
{% endhint %}

Make a folder to store your Narrative in the Project pane (ours is named `Narrative`), and then inside that folder, create a new Yarn Project asset:

<figure><img src="../../.gitbook/assets/dialoguewheel2.png" alt="" width="528"><figcaption><p>Creating a new Yarn Project asset in the Project pane.</p></figcaption></figure>

Similarly, also in the `Narrative` folder, create a new Yarn Script to use:

<figure><img src="../../.gitbook/assets/dialoguewheel3.png" alt="" width="531"><figcaption><p>Creating a new Yarn Script asset in the Project pane.</p></figcaption></figure>

Name both the Yarn Project and the Yarn Script something appropriate. Open the Yarn script to write your story. Then save the Yarn script and return to Unity.

We've provided an initial sample story here, if you want to test things out.

<details>

<summary>Initial sample story for Six-Segment Dialogue Wheel</summary>

{% code title="WheelDemoScript.yarn" overflow="wrap" %}
```xml
title: Start
---
Narrator: What brings to the pool?
-> Cleaning
    I have come to clean the pool.
    Narrator: Ah, just as I thought.
        -> I'm a pool cleaner
            Narrator: I know.
            <<jump End>>
        -> I was actually lying.
            Narrator: Oh, I see.
            <<jump End>>
-> Treasure 
    I am looking for the lost treasure of... the pool.
    Narrator: There is no treasure in the pool.
        -> WHAT!?
            WHAT?! WHY NOT? I WAS TOLD THERE WAS TREASURE HERE!
            Narrator: Nope. 
            <<jump End>>
        -> Oh, okay.
            Oh, well, I guess I'll go.
            Narrator: OK, bye!
            <<jump End>>
        -> I know.
            I know, I just wanted a swim.
            Narrator: In you get, then!
            <<jump End>>
-> No reason
    I have a fetish for pool cleaning equipment.
    Narrator: Whatever floats your boat...
        -> Thanks.
            Narrator: Uh uh.
            <<jump End>>
-> Commerce
    I'd like to buy a pool.
    Narrator: Well, it's not for sale.
    Narrator: Go away.
    <<jump End>>
-> Swimming
    I'm here to go for a swim. 
    Narrator: Well, you can't.
    <<jump End>>
===
title: End
---
Narrator: Anyway...
Narrator: Have a nice day!
<<stop>>
===
```
{% endcode %}

</details>

With the Dialogue Runner selected in the Hierarchy, drag the Yarn Project that you created from the Project pane into the Yarn Project slot in the Dialogue System's Inspector:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-23 at 3.35.57 pm.png" alt="" width="563"><figcaption><p>Assigning your Yarn Project to the Dialogue System.</p></figcaption></figure>

Next, locate the Image Dialogue Wheel prefab, supplied with this add-on, and drag it from the Project pane, so it's below the Canvas in the Hierarchy:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-23 at 3.40.45 pm.png" alt="" width="516"><figcaption><p>The Image Dialogue Wheel, added below the Canvas of the Dialogue System.</p></figcaption></figure>

Right-click on the Options Presenter in the Hierarchy, and choose Delete. You won't need that view, as you'll be displaying a wheel instead of a list.

To make the Dialogue System aware of the Six-Segment Dialogue Wheel, select it (the Dialogue System) in the Hierarchy, and drag the Image Dialogue Wheel from the Hierarchy into the Element 2 slot of the Dialogue Views section in the Inspector:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-23 at 3.41.53 pm.png" alt="" width="563"><figcaption><p>Adding the Image Dialogue Wheel to the Dialogue System.</p></figcaption></figure>

Finally we want to set our story to start automatically, click on the Start Automatically toggle on the Dialogue Runner Inspector and from the Start Node drop down pick `Start`.
If you save your scene and run it, your Image Dialogue Wheel should now be working!

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-23 at 3.46.55 pm.png" alt=""><figcaption><p>The Image Dialogue Wheel in action.</p></figcaption></figure>

## Customising the Six-Segment Dialogue Wheel

You can specify which position on the wheel your dialogue appears using [tags in your Yarn scripts](../../getting-started/writing-in-yarn/tags-metadata.md). Specifically, you can add tags to each set of options to specify where in the wheel the option should be placed.

For example, the following Yarn script:

```
title: Start
---
Narrator: Show me the positions on the Six-Segment Wheel?
    -> Left Top #lt
    -> Left Middle #lm
    -> Left Bottom #lb
    -> Right Top #rt
    -> Right Middle #rm
    -> Right Bottom #rb
===
```

Results in this:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-23 at 3.54.00 pm.png" alt="" width="563"><figcaption></figcaption></figure>

If you select the Image Dialogue Wheel Prefab in the Hierarchy (under Dialogue System), you can look to the Inspector to customise these tags, among other options:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-23 at 3.57.45 pm.png" alt="" width="563"><figcaption></figcaption></figure>

You can also use the Yarn Command `<<set-opt>>` before each group of options in your Yarn scripts to specify how many options (limited to a maximum of three on either side) should appear in each column (left or right).

For example, the following Yarn Script:

<pre><code>title: Start
---
Narrator: Show some options?
<a data-footnote-ref href="#user-content-fn-1">&#x3C;&#x3C;set-opt 1 3>></a>
-> I'm an option! 
-> I'm another option!
-> I'm yet another option!
-> Me too!
===
</code></pre>

Will result in this:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-23 at 4.01.36 pm.png" alt="" width="563"><figcaption></figcaption></figure>

{% hint style="info" %}
If you use `set-opt` to specify more options than the six-segment wheel can handle (i.e. a maximum of 3 options on each side), things may not work as expected
{% endhint %}

Review the [provided Image Dialogue Wheel Example for more information](dialogue-wheel-examples.md), or check out the guide on [Using Auto-Layout Dialogue Wheel](using-auto-layout-wheel.md).

[^1]: Using `set-opt` to specify 1 option should be on the left, and 3 on the right.
