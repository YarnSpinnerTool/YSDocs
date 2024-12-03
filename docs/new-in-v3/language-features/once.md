---
description: >-
  Learn about once statements, which let you specify content that only runs
  once.
---

# Once

<figure><img src="../../.gitbook/assets/Once Statements.png" alt=""><figcaption></figcaption></figure>

In Yarn Spinner 3, you can use a `once` statement to run content only one time. When the script reaches a `once` statement, it checks to see if it’s run before. If it has, it skips over it! Magic.

{% hint style="info" %}
`once` statements are great for making sure that the player never sees certain content more than once. For example, you might want a character to never introduce themselves to the player twice.
{% endhint %}

There are two main ways you can use a `once` statement.&#x20;

### You can wrap some lines in `<<once>>` and `<<endonce>>`:

```html
<<once>>
  // The guard will introduce herself to the player only once. 
  Guard: Hail, traveller! Well met.
  Guard: I am Alys, the guard!
<<endonce>>
```

You can also use an `<<else>>` clause within the `<<once>>` statement, which will be run if the relevant `<<once>>` content has already been seen:

```html
<<once>>
  Guard: Hail, traveller! Well met.
<<else>>
  Guard: Welcome back.
<<endonce>>
```

You can also add an `if` to the `once` to run content a single time, but only when a certain condition is true. In all other cases, it will be skipped (or the `else` content will be run, if there is any):

```html
<<once if $player_is_adventurer>>
  // The guard knows the player is an adventurer, so say this line, 
  // but only ever once!
  Guard: I used to be an adventurer like you, but then I took an arrow in the knee.
<<else>>
	// Either the player is not an adventurer, or we already saw the 
	// 'arrow in the knee' line.
	Guard: Greetings.
<<endonce>>
```

### You can add `<<once>>` to a line, or options:

If you add `once` (or `once if`) to a line, that line will only appear once, and will be skipped over every other time it’s encountered:

```html
Guard: Who are you? <<once>> // Show this line only one time
Guard: Go on, get lost!
```

Similarly, if you add it to an option, that option will only be selectable once, and will be marked as unavailable after it’s been selected.

```html
-> What's going on? <<once>>
	Guard: The kingdom is under seige!
-> Where can I park my horse? <<once if $has_horse>>
	Guard: Over by the tavern.
-> Lovely day today!
	Guard: Uh huh.
-> I should go.
	Guard: Please do.
```

`once` statements are really useful when you want to show long, detailed content the first time it’s encountered, but you don’t want to show it every time. This means that players don’t need to mash the ‘skip line’ button over and over when they realise that they’re starting to see a long run of lines they’ve already seen:

<pre class="language-html"><code class="lang-html"><strong>&#x3C;&#x3C;once>>
</strong>	// Show long, character-establishing lines the first time
	Guard: There's nothing new to report!
	Guard: I've been at this post for hours, and I'm so bored.
	Guard: I can't wait for the end of my watch.
&#x3C;&#x3C;else>>
	// Show a more condensed version all other times
	Guard: Nothing to report!
&#x3C;&#x3C;endonce>>
</code></pre>

{% hint style="info" %}
`once` statements keep the information about whether they’ve been run or not in a variable that’s stored in your Dialogue Runner’s Variable Storage, just like any other variable. The variable isn’t directly accessible from your Yarn scripts.
{% endhint %}

