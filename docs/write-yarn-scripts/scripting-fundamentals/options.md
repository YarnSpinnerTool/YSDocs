---
description: Learn to use options, which allow your players to choose lines of dialogue.
icon: arrow-right-long
---

# Options

When you want to let the player decide what to say, you use an **option**. Options let you show multiple potential lines of dialogue to the player, and let the player select one.

Options are lines prefixed with a `->`. You write as many options as you'd like the player to see, and the player chooses one of them. The content of the option is like any other line of dialogue.

For example, consider the following code:

{% code title="Demo.yarn" overflow="wrap" lineNumbers="true" %}
```css
title: Start
---
Navigator: The quantum fluctuations are intensifying. We need to jump now.
Captain: But the calculations aren't complete. We could end up anywhere.
Navigator: The wormhole is collapsing. It's now or never.
Captain: Fine. Initiate jump sequence.
Navigator: Something's wrong. We're being pulled backward...
Captain: That's impossible. Unless...
Navigator: We're arriving before we left. We've become our own rescue mission.
-> Captain: Let's alter our trajectory and break this temporal loop!
-> Captain: We must complete the cycle. Our past selves depend on it.
===
```
{% endcode %}

In this example, the line `Navigator: We're arriving before we left. We've become our own rescue mission.` will run.&#x20;

The player will then be given the choice for the Captain to say either `Let's alter our trajectory and break this temporal loop!`, or `We must complete the cycle. Our past selves depend on it.`

Options that are grouped together are delivered together, for example, consider the following updated script:

{% code title="Demo.yarn" overflow="wrap" lineNumbers="true" %}
```css
title: Start
---
Navigator: The quantum fluctuations are intensifying. We need to jump now.
Captain: But the calculations aren't complete. We could end up anywhere.
Navigator: The wormhole is collapsing. It's now or never.
Captain: Fine. Initiate jump sequence.
Navigator: Something's wrong. We're being pulled backward...
Captain: That's impossible. Unless...
Navigator: We're arriving before we left. We've become our own rescue mission.
-> Captain: Let's alter our trajectory and break this temporal loop!
-> Captain: We must complete the cycle. Our past selves depend on it.
Navigator: Ayee! We're all going to die!
-> Captain: Nonsense! Keep yourself together!
-> Captain: AHHHH! We're all going to die!
===
```
{% endcode %}

In this example script these two options will be delivered together:

```yarnspinner
-> Captain: Let's alter our trajectory and break this temporal loop!
-> Captain: We must complete the cycle. Our past selves depend on it.
```

As will these, separately:

```
-> Captain: Nonsense! Keep yourself together!
-> Captain: AHHHH! We're all going to die!
```

<figure><img src="../../.gitbook/assets/demo.gif" alt=""><figcaption><p>Two sets of options in the same node being displayed separately.</p></figcaption></figure>

### Options and Lines

Options can have their own lines, which are run when the option is selected. If a different option is selected, they won't run. To write this, _indent_ the lines that belong to an option.

In the following code, different lines will run based on which of the two shortcut options are selected.

```css
title: Start
---
Navigator: The quantum fluctuations are intensifying. We need to jump now.
Captain: But the calculations aren't complete. We could end up anywhere.
Navigator: The wormhole is collapsing. It's now or never.
Captain: Fine. Initiate jump sequence.
Navigator: Something's wrong. We're being pulled backward...
Captain: That's impossible. Unless...
Navigator: We're arriving before we left. We've become our own rescue mission.
-> Captain: Let's alter our trajectory and break this temporal loop!
    Navigator: Risky, Captain. We'd be writing ourselves out of existence.
-> Captain: We must complete the cycle. Our past selves depend on it.
    Navigator: Then we're doomed to repeat this moment... forever.
===
```

When the player has the choice of saying either "`Let's alter our trajectory and break this temporal loop!`", or "`We must complete the cycle. Our past selves depend on it.`"&#x20;

Depending on their choice, the Navigator will say "`Risky, Captain. We'd be writing ourselves out of existence.`" or "`Then we're doomed to repeat this moment... forever.". Finally, no matter what was selected, the line "Sounds good!`" will run.

### Options within Options

You can also nest options below other options. For example, consider the following snippet of Yarn Spinner Script:

{% code overflow="wrap" lineNumbers="true" %}
```css
title: Start
---
Navigator: The quantum fluctuations are intensifying. We need to jump now.
Captain: But the calculations aren't complete. We could end up anywhere.
Navigator: The wormhole is collapsing. It's now or never.
Captain: Fine. Initiate jump sequence.
Navigator: Something's wrong. We're being pulled backward...
Captain: That's impossible. Unless...
Navigator: We're arriving before we left. We've become our own rescue mission.
-> Captain: Let's alter our trajectory and break this temporal loop!
    Navigator: Risky, Captain. We'd be writing ourselves out of existence.
    -> Captain: Damnit, Navigator! Nothing can stop me existing!
        Navigator: *sigh* Very well, Captain.
    -> Captain: By gods! You're right!
        Navigator: But it's only solution, I fear.
-> Captain: We must complete the cycle. Our past selves depend on it.
    Navigator: Then we're doomed to repeat this moment... forever.
    -> Captain: If we're doomed, at least we'll be remembered as heroes.
        Navigator: .. if anyone remembers us at all
    -> Captain: Forever... forever... forever...
        Navigator: Sir?
    -> Captain: We must do it!
            Navigator: As always, sir, you're right.
===
```
{% endcode %}

In this example script, the following options will be delivered together:

```
-> Captain: Let's alter our trajectory and break this temporal loop!
-> Captain: We must complete the cycle. Our past selves depend on it.
```

And then, depending on which one was chosen, another set of options will be delivered together.&#x20;

For example, if the player chooses `Captain: Let's alter our trajectory and break this temporal loop!` , then the line from the Navigator will be delivered (`Navigator: Risky, Captain. We'd be writing ourselves out of existence.` ) and then two options for the Captain will be provided:

<pre><code><strong>-> Captain: Damnit, Navigator! Nothing can stop me existing!
</strong>-> Captain: By gods! You're right!
</code></pre>

And if the player chooses `Captain: We must complete the cycle. Our past selves depend on it.` , then the line from the Navigator will be delivered (`Navigator: Then we're doomed to repeat this moment... forever.`) and then three options for the Captain will be provided:

```
-> Captain: If we're doomed, at least we'll be remembered as heroes.
-> Captain: Forever... forever... forever...
-> Captain: We must do it!
```

<figure><img src="../../.gitbook/assets/Screenshot 2025-04-16 at 12.23.09 pm.png" alt=""><figcaption><p>The different groups of options, showing when they're grouped using colours.</p></figcaption></figure>

## Testing out Options

{% stepper %}
{% step %}
### Add options to your tiny narrative.

Consider adding some lines that belong to the options below them, too.
{% endstep %}

{% step %}
### Run your single-node narrative using Preview

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-07 at 1.56.45 pm.png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}
