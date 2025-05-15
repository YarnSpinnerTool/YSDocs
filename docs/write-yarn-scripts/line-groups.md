---
description: >-
  Learn about using line groups, which allow Yarn Spinner to choose which
  content to run, depending on conditions.
icon: grip-lines
---

# Line Groups

To give your dialogue more life and variety, you can also provide lines in a **line group**. When lines are in a line group, Yarn Spinner will choose one of them for you.

Line groups are collections of lines that begin with a `=>` symbol:

{% code overflow="wrap" lineNumbers="true" %}
```markup
title: Start
---
Captain: Navigator, fire the glitter torpedoes! That'll confuse the enemy ships!
=> Navigator: *sighs deeply* Sir, we don't have 'glitter torpedoes.' Those were in your dream last night.
=> Navigator: *eyes roll skyward* Captain, weaponizing craft supplies is not part of standard space combat protocol.
=> Navigator: *Slumps shoulders in defeat* I'll... make a note in the log that you suggested tactical glitter, sir.
===
```
{% endcode %}

In this example, the Captain will say "`Navigator, fire the glitter torpedoes! That'll confuse the enemy ships!`", and then Yarn Spinner will choose one of the subsequent lines to respond with.

{% hint style="info" %}
Line groups are great for running ‘barks’ - collections of short lines that need to run in response to an in-game event. It can be useful to think of them like Yarn Spinner’s existing options `->` syntax, but instead of the player choosing which content to run, the computer picks it for you:

```
=> Guard: Halt!
=> Guard: No entry!
=> Guard: Stop!
```
{% endhint %}

You can attach conditions to lines in a line group, to ensure that they only run when it’s appropriate to do so. Conditions can be any true or false expression, and can also be combined with the `once` keyword to ensure that a line can only run once:

<pre class="language-html" data-overflow="wrap"><code class="lang-html">=> Guard: Greetings, citizen.
<strong>=> Guard: Hello, traveller.
</strong>	Guard: Stay vigilant. // runs after 'Hello, traveller.'
=> Guard: Hail, adventurer! &#x3C;&#x3C;if $player_is_adventurer>>
=> Guard: I used to be an adventurer like you, but then I took an arrow in the knee. &#x3C;&#x3C;once if $player_is_adventurer>>
</code></pre>

{% @yarnspinner/tryyarnspinner id="https://try.yarnspinner.dev/embed?gist=2deb278dae6a6f679b3d7eae1e9b41fd" %}

A line in a line group can also have additional lines belonging to it, which will run if the item is selected.
