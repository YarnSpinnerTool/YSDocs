---
description: >-
  Learn how to use the Live Share Extension with Yarn Spinner for Visual Studio
  Code.
icon: people-carry-box
---

# Writing Together

The primary editing experience for Yarn Spinner is our Yarn Spinner for Visual Studio Code extension. This provides the majority of features that you'd want in order to effectively write `.yarn` scripts using VSCode.&#x20;

This guide shows you how to use [Microsoft's free Live Share extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare), together with Yarn Spinner for Visual Studio Code, to collaborate live on your narrative.

<figure><img src="../../../.gitbook/assets/Screen Shot 2023-12-13 at 1.09.44 pm.jpeg" alt=""><figcaption><p>Live collaboration on <code>.yarn</code> files using the Live Share extension and VIsual Studio Code</p></figcaption></figure>

{% hint style="info" %}
The rest of this guide assumes you've followed the steps in [.](./ "mention"), and already have the Yarn Spinner for Visual Studio Code extension up and running.
{% endhint %}

## Installing Live Share

To install Live Share for Visual Studio Code, and use it with Yarn Spinner:

1. [Setup Yarn Spinner for Visual Studio Code.](./)
2. Click [this link](vscode:extension/MS-vsliveshare.vsliveshare) to open Visual Studio Code, and jump to the Live Share Extension.
3. Click the install button!

{% hint style="warning" %}
If Step 2 does not work, launch Visual Studio Code and choose the View menu -> Extensions, to open the Extensions Marketplace.&#x20;

Then, in the search field at the top-left of the window, search for "Live Share", and click the Install button on the extension provided by Microsoft that appears in the results.
{% endhint %}

## Inviting collaborators

Open your Yarn Spinner project in Visual Studio code. For example, here's [I Feel Fine](https://store.steampowered.com/app/2150850/I_Feel_Fine/):

<figure><img src="../../../.gitbook/assets/Screenshot 2023-12-13 at 1.15.49 pm.png" alt=""><figcaption><p>A project open in Visual Studio Code, with lots of <code>.yarn</code> files</p></figcaption></figure>

With your project open, choose Live Share in the Activity Bar on the left side of the screen, and in the resulting view that appears, choose the Share button:

<figure><img src="../../../.gitbook/assets/Screenshot 2023-12-13 at 1.16.29 pm.png" alt="" width="263"><figcaption><p>The Live Share button in the Activity Bar, and the Share button.</p></figcaption></figure>

You'll be prompted to sign in to either GitHub or your Microsoft account, and after this a notification will appear in the bottom of the screen letting you know a shareable link to collaborate has been copied to the clipboard:

<figure><img src="../../../.gitbook/assets/Screenshot 2023-12-13 at 1.20.38 pm.png" alt="" width="563"><figcaption><p>The notification that your workspace is being shared.</p></figcaption></figure>

## Joining a shared workspace

When you receive a collaboration link and visit it, you'll be asked how you'd like to join:

<figure><img src="../../../.gitbook/assets/Screen Shot 2023-12-13 at 1.05.35 pm.jpeg" alt="" width="563"><figcaption><p>Joining a shared workspace.</p></figcaption></figure>

If you choose to Continue in Web, you'll be taken to a web version of VS Code, which will not have the Yarn Spinner extension installed. If you click Open in Visual Studio Code, your local copy of VS Code will be installed, complete with extensions.

{% hint style="info" %}
This guide assumes that the person you're sharing with also has the Yarn Spinner for Visual Studio Code extension installed.
{% endhint %}

Once the shared workspace opens in your local copy of VS Code, you'll be in an untrusted state, which means the Yarn Spinner extension will not be providing syntax highlighting, To enable this, click Manage, in the grey bar at the top of the window, then click the Trust button in the view that appears:

<figure><img src="../../../.gitbook/assets/Screen Shot 2023-12-13 at 1.06.59 pm (1).png" alt=""><figcaption><p>Trusting the shared workspace.</p></figcaption></figure>

## Writing together

The person who initially shared the workspace will have full and complete access to the features of the Yarn Spinner for Visual Studio Code extension. Everything, from syntax highlighting to the graph view will work as normal.

Those who are joining the shared session will only have access to the syntax highlighting features of the Yarn Spinner for Visual Studio Code extension, provided they go through the process of trusting the workspace, as noted earlier.

As you edit, you'll be able to see other users in the files, and their work will be briefly highlighted as they write:

<figure><img src="../../../.gitbook/assets/Screenshot 2023-12-13 at 1.09.21 pm.png" alt=""><figcaption><p>Editing <code>.yarn</code> files together.</p></figcaption></figure>

## For more help

For more guidance using the Live Share extension, check out [the extension's official page](https://code.visualstudio.com/docs/getstarted/userinterface), as well as the [Live Share extension's documentation](https://code.visualstudio.com/learn/collaboration/live-share).

{% hint style="info" %}
We'll be improving the capabilities of Yarn Spinner for Visual Studio Code over time, and will add features that directly support the Live Share extension. Stay tuned!
{% endhint %}
