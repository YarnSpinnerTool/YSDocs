---
description: Learn to use options, which allow your players to choose lines of dialogue.
icon: arrow-right-long
---

# Options

## Options

When you want to let the player decide what to say, you use an **option**. Options let you show multiple potential lines of dialogue to the player, and let the player select one.

Options are prefixed with a `->`. You write as many options as you'd like the player to see, and the player chooses one of them. The content of the option is like any other line of dialogue.

For example, consider the following code:

{% code title="" overflow="wrap" lineNumbers="true" %}
```markup
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

In this example, the line "`Navigator: We're arriving before we left. We've become our own rescue mission.`" will run. The player will then be given the choice for the Captain to say either "`Let's alter our trajectory and break this temporal loop!`", or "`We must complete the cycle. Our past selves depend on it.`"

### Options and Lines

Options can have their own lines, which are run when the option is selected. If a different option is selected, they won't run. To write this, _indent_ the lines that belong to an option.

In the following code, different lines will run based on which of the two shortcut options are selected.

```
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

{% stepper %}
{% step %}
### Using Try Spinner, add some options to your tiny narrative.

Consider adding some lines that belong to the options below them, too.
{% endstep %}

{% step %}
### Run your single-node narrative using Try Yarn Spinner

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-07 at 1.56.45 pm.png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}

### Nested Options

In addition to containing lines, options can also contain _other_ options.

{% code overflow="wrap" lineNumbers="true" %}
```markup
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
-> Captain: We must complete the cycle. Our past selves depend on it.
    Navigator: Then we're doomed to repeat this moment... forever.
    -> Captain: If we're doomed, at least we'll be remembered as heroes.
        Navigator: .. if anyone remembers us at all
===
```
{% endcode %}
