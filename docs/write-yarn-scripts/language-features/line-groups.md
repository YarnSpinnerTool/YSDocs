---
description: >-
  Learn about using line groups, which allow Yarn Spinner to choose which
  content to run, depending on conditions.
---

# Line Groups

In Yarn Spinner 3, you can now create line groups. A line group is collection of lines that Yarn Spinner will choose from.&#x20;

{% embed url="https://try.yarnspinner.dev/?gist=2deb278dae6a6f679b3d7eae1e9b41fd" %}
Try a sample of Line Groups online in Try Yarn Spinner.
{% endembed %}

Line groups are collections of lines that begin with a `=>` symbol:

```
=> Hello! Welcome to my shop!
=> Hi! I'm the blacksmith!
=> Welcome to the blacksmith!
```

When Yarn Spinner encounters a line group, it will select one of the lines in the group and run it. &#x20;

{% hint style="info" %}
Line groups are great for running ‘barks’ - collections of short lines that need to run in response to an in-game event. It can be useful to think of them like Yarn Spinner’s existing options `->` syntax, but instead of the player choosing which content to run, the computer picks it for you:

```
=> Guard: Halt!
=> Guard: No entry!
=> Guard: Stop!
```
{% endhint %}

You can attach conditions to lines in a line group, to ensure that they only run when it’s appropriate to do so. Conditions can be any true or false expression, and can also be combined with the `once` keyword to ensure that a line can only run once:

```html
=> Guard: Greetings, citizen.
=> Guard: Hello, traveller.
	Guard: Stay vigilant. // runs after 'Hello, traveller.'
=> Guard: Hail, adventurer! <<if $player_is_adventurer>>
=> Guard: I used to be an adventurer like you, but then I took an arrow in the knee. <<once if $player_is_adventurer>>
```

A line in a line group can also have additional lines belonging to it, which will run if the item is selected.
