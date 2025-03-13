---
description: Understand the Intro sample.
---

# Intro

After you've worked through the Beginner's Guide, the Intro Sample is a great place to go next.

Intro is a simple conversation featuring branching, variables, localisation, a themed Line View and Option View, and voice-over.

## Structure of the scene

To understand the Intro Sample, open it and take a look at the Hierarchy:

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-29 at 4.47.37 pm.png" alt="" width="509"><figcaption></figcaption></figure>

You'll find the following:

* **Dialogue Runner** — a GameObject with a [dialogue-runner.md](../components/dialogue-runner.md "mention"), an [audio-line-provider.md](../components/line-provider/audio-line-provider.md "mention"), and a script to allow the game to be quit attached to it.
  * The [dialogue-runner.md](../components/dialogue-runner.md "mention") is a Component supplied by the Yarn Spinner for Unity Package.
  * The [audio-line-provider.md](../components/line-provider/audio-line-provider.md "mention") is a Component supplied by the Yarn Spinner for Unity Package.
