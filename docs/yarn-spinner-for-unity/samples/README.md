---
description: Learn about the samples we provide for Yarn Spinner for Unity.
icon: gift
---

# Samples

Yarn Spinner for Unity ships with a range of samples covering common patterns for things you might want to do in your game. The samples are not included with the Yarn Spinner for Unity package, so if you want to explore them, you'll need to manually their package.

<figure><img src="../../.gitbook/assets/welcome.png" alt=""><figcaption></figcaption></figure>

## Adding the Samples Packge to a Project

To install the Yarn Spinner for Unity Samples, you'll need to have a Unity project with [Yarn Spinner installed ](../installation-and-setup/)installed. Once Yarn Spinner for Unity is installed, you can install the Yarn Spinner for Unity Samples Package.

How you install the Samples depends on how you installed Yarn Spinner:

-— partial instructions---

## 🚧 Installing the Samples

For version 3 of Yarn Spinner the samples have been removed from the main repository and made a standalone package.\
We did this because as the samples were growing they were becoming a larger and larger portion of the install, this was essentially bloating an install of Yarn Spinner while at the same time making development slower and more annoying.\
The samples are a necessary element of Yarn Spinner so instead of being treated like an afterthought they have been spun out into their own thing.\
Now they can be developed, improved, tested, have their own dependancies, and share a common sample codebase without needing to impact the rest of Yarn Spinner, meaning more—and better—samples than in the past.

The best way to install the samples is to use the Samples button on the inspector of any Dialogue Runner, Yarn Project, or Yarn Script.\
Or by navigating to `Window -> Yarn Spinner -> Install Samples Package`.

![Inspector for a Yarn Project](../../.gitbook/assets/ism-01.png)

Clicking on this will work out the best way to install the samples depending on how you installed Yarn Spinner itself.

#### Manually Installing the Samples

While the best way to install samples is the above, depending on your environment and device setup this might not be possible.\
In those circumstances you will need to manually install the samples, which is what this section is about.

{% hint style="info" %}
This is a standard unity package so if you have a workflow around packages this will just work with it.
{% endhint %}

1. Inside your browser navigate to the samples site: https://github.com/YarnSpinnerTool/YarnSpinner-Unity-Samples
2. Click on the Code button and from the dropdown select the Download Zip option

![Downloading the samples from GitHub](../../.gitbook/assets/ism-02.png)

3. Save this zip somewhere useful and unzip it

This folder now contains the samples package and it's time to add it to your Unity project.

4. Back inside Unity open the package manager from the menu `Windows -> Package Manager`
5. In the top left corner press the `+` button and from the dropdown that appears select `Install package from disk`

![Adding a local package to the package manager](../../.gitbook/assets/ism-03.png)

6. Navigate to where you downloaded and unzipped the samples and select the `package.json` file inside that folder

Unity will now install the samples project after a little while.\
Once it is done you can now browse and install the samples directly from the package manager.

7. select the samples package in the middle column and click on the Samples tab in the main window.

![Perusing the samples within the package manager](../../.gitbook/assets/ism-04.png)

And just like that you can now install and explore the samples!

\--end partial instrucitons---

{% tabs %}
{% tab title="Unity Asset Store" %}
TODO
{% endtab %}

{% tab title="Itch.io" %}

{% endtab %}

{% tab title="Other" %}

{% endtab %}
{% endtabs %}

{% hint style="info" %}
Adding the Yarn Spinner Samplesfor Unity package to your Unity project **does not give you access to the samples**. You must install the Samples you want after adding the Yarn Spinner
{% endhint %}

Once the Yarn Spinner Samples package is installed in your project, you can install each individual Sample by opening the Unity Package Manager through the Window menu -> Package Manaing, locating the Yarn Spinner Samples package, and switching to the Samples tab:

<figure><img src="../../.gitbook/assets/Screenshot 2025-05-15 at 5.18.37 pm.png" alt=""><figcaption><p>Locating the Yarn Spinner Samples in the Unity Package Manager, after installing the Yarn Spinner Samples Package into a project.</p></figcaption></figure>

## Accessing a Sample

To work with each individual Yarn Spinner for Unity Sample, click the Import button next to the Sample that you want to install, inside the Unity Package Manager. For example, to add the [Feature Tour](feature-tour.md) sample to the project, click its Import button:

<figure><img src="../../.gitbook/assets/Screenshot 2025-05-15 at 5.22.23 pm.png" alt=""><figcaption><p>Click the Import button next to the Sample you want to install.</p></figcaption></figure>

You'll find the Sample in the Project pane:

<figure><img src="../../.gitbook/assets/Screenshot 2025-05-15 at 5.26.40 pm.png" alt=""><figcaption></figcaption></figure>

You can open the Unity Scene (in this case `Main`) to explore the sample.

## List of Yarn Spinner for Unity Samples

* [Welcome](intro.md) - a small scene in which a character explains Yarn Spinner's inbuilt samples and what each of the others include.
* [Feature Tour](feature-tour.md) - walks through the various major features of Yarn Spinner.
* [Basics Storylets and Saliency](basics-storylets-and-saliency.md) - demonstrates the creation of pools of lines or nodes which can be drawn from based on current game state to deliver dynamic, contextual content.
* [Theming Default Views](theming-default-views.md) - demonstrates basic customisation of dialogue views with a custom font, view background, and continue button texture.
* [Create a Phone Chat View](page-1.md) - demonstrates more elaborate customisation of dialogue views such that they are styled like a text message conversation on a phone screen. This includes how to add lines or options to the screen when a new line is received, as opposed to the default view which replaces the previous line or options.
* [Make Options That Timeout](make-options-timeout.md) - demonstrates creation of custom options view and behaviour such that the player is given only a limited amount of time to choose once dialogue options are presented.
* [Voice Over and Localisation](sample-guide-voice-over-and-localisation.md) - demonstrates localising a dialogue view
* [Background Chatter](background-chatter.md) - demonstrates the use of multiple Dialogue Runners to allow different types of NPC background conversations simultaneously with each other or during primary dialogue.
* [Inline Events](inline-events.md) - demonstrates the use of Action Markup to insert command-like triggers in the middle of dialogue line delivery.
* [Replacement Markup](replacement-markup.md) - demonstrates the use of Replacement Markup to insert text styling or dynamic content into dialogue lines as they are presented.
* [Custom Saliency Strategies](custom-saliency-strategies.md) - demonstrates the creation of a custom way to score and choose between content in node or line groups at runtime.
* [Advanced Saliency](advanced-saliency.md) - demonstrates the use of node groups, line groups, and dynamic line content together to make a fully dynamic scene.
