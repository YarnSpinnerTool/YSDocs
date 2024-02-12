---
description: >-
  Learn how to use the Six-Segment Dialogue Wheel, from the Dialogue Wheel for
  Yarn Spinner Add-On Package.
---

# Using Six-Segment Wheel

The Six-Segment Dialogue Wheel provides a dialogue wheel with a light sci-fi appearance, and can display up to six responses for your dialogue. You can specify exactly which segment of the wheel each response is located.

## Using the Six-Segment Dialogue Wheel

To use the Six-Segment Dialogue Wheel [make sure your Unity project has the Yarn Spinner package installed](../../yarn-spinner-for-unity/installation-and-setup.md), and the [install the Dialogue Wheel for Yarn Spinner package](installing-dialogue-wheel.md).

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
```
{% endcode %}

</details>

Back in Unity, choose the Dialogue Runner that you added to the Hierarchy, right-click it and choose Prefab -> Unpack.&#x20;

{% hint style="info" %}
Unpacking the Dialogue Runner prefab is exactly the same as creating your own empty GameObject and then adding Dialogue Runner and In Memory Variable Storage components to it.
{% endhint %}

This will allow you to modify the contents of the (former) prefab, in order to add the Six-Segment Dialogue Wheel as a Dialogue View.

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-23 at 3.35.04 pm.png" alt="" width="563"><figcaption><p>Unpacking the Dialogue System prefab.</p></figcaption></figure>

With the Dialogue Runner selected in the Hierarchy, drag the Yarn Project that you created from the Project pane into the Yarn Project slot in the Dialogue System's Inspector:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-23 at 3.35.57 pm.png" alt="" width="563"><figcaption><p>Assigning your Yarn Project to the Dialogue System.</p></figcaption></figure>

Next, locate the Six-Segment Dialogue Wheel prefab, supplied with this add-on, and drag it from the Project pane, so it's below the Canvas in the Hierarchy:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-23 at 3.40.45 pm.png" alt="" width="516"><figcaption><p>The Six-Segment Dialogue View, added below the Canvas of the unpacked Dialogue System.</p></figcaption></figure>

Right-click on the Options List View in the Hierarchy, and choose Delete. You won't need that view, as you'll be displaying a wheel instead of a list.&#x20;

To make the Dialogue System aware of the Six-Segment Dialogue Wheel, select it (the Dialogue System) in the Hierarchy, and drag the Six-Segment Dialogue View from the Hierarchy into the Element 1 slot of the Dialogue Views section in the Inspector:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-23 at 3.41.53 pm.png" alt="" width="563"><figcaption><p>Adding the Automatic-Layout Dialogue Wheel to the Dialogue System.</p></figcaption></figure>

If you save your scene and run it, your Six-Segment Dialogue Wheel should now be working!

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-23 at 3.46.55 pm.png" alt=""><figcaption><p>The Automatic-Layout Dialogue Wheel in action.</p></figcaption></figure>

## Customising the Six-Segment Dialogue Wheel

You can specify which position on the wheel your dialogue appears using [tags in your Yarn scripts](../../writing-dialogue-in-yarn/writing-in-yarn/tags-metadata.md). Specifically, you can add tags to each set of options to specify where in the wheel the option should be placed.&#x20;

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

If you select the Six-Segment Dialogue Wheel Prefab in the Hierarchy (under Dialogue System), you can look to the Inspector to customise these tags, among other options:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-23 at 3.57.45 pm.png" alt="" width="563"><figcaption></figcaption></figure>

You can also use the Yarn Command `<<set-opt>>` before each group of options in your Yarn scripts to specify how many options (limited to a maximum of three on either side) should appear in each column (left or right).

For example, the following Yarn Script:

<pre><code>title: Start
---
Narrator: Show some options?
  <a data-footnote-ref href="#user-content-fn-1">  &#x3C;&#x3C;set-opt 1 3>></a>
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

Review the [provided Six-Segment Dialogue Wheel Example for more information](dialogue-wheel-examples.md), or check out the guide on [Using Auto-Layout Dialogue Wheel](using-auto-layout-wheel.md).

[^1]: Using `set-opt` to specify 1 option should be on the left, and 3 on the right.
