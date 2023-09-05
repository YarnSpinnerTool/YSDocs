# Writing the script

## Writing your Yarn Script

Next, we need to actually write some content — a script — in Yarn. This script will be parsed by Yarn Spinner, and used to drive the story in our game.

* With the Intro script we created a moment ago open, you should see a placeholder that looks something like this:

{% code title="Intro.yarn" %}
```text
title: Intro
tags:
---

=== 
```
{% endcode %}

* Add the following immediately below the `---` \(leave the `===` at the end\):

```text
Tom: Uh... hello?
Tom: Is anyone there?
Anne: Hi there!
```

This Yarn Script presents lines from Tom, who says two things, followed by Anne, who says one thing. Each of these lines is, somewhat helpfully, referred to as a **line** by Yarn Spinner. 

The fact that each of these lines has a character name associated with it \(Tom and Anne\) is not strictly a feature of Yarn Spinner, but makes it easier to identify characters as you work with you script.

* Next, add some options for the player to respond with:

```text
-> Tom: Who are you?
    Tom: And where are you?
    Anne: I'm Anne! I'm right here!
    <<set $knows_anne_name to true>>

-> Tom: Where am I?
    Anne: You're floating in a featureless void!
    Tom: I can see that...
```

This Yarn Script presents the lines prefixed with `->` \(a dash, followed by a greater-than sign\) as choices. A line prefixed with the `->` is called a **shortcut option**.

A shortcut option can have as many lines of its own as you want, these will be run when the shortcut option is selected. The lines that belong to a shortcut option are _indented_ below the shortcut option.

In this case, after Anne says "Hi there!", the player will be presented with two options for what Tom says next: "Who are you?" or "Where am I?"

Depending on which of those options the player chooses, the lines under the chosen option will be run. So, if the player chooses for Tom to say "Where am I?", Anne will reply with "You're floating in a featureless void!" and Tom will then say "I can see that..."

You'll notice some new syntax in the first shortcut option: `<<set $knows_anne_name to true>>.`

You can store information about the state of your game in **variables**. Variables store information; more specifically, they can store text, numbers, true or false values, or `null` \(which represents ‘no value’\).

To set the value of a variable, you use the `set` keyword. In this cases, we set a variable called `$knows_anne_name` to `true`. 

* Next, add some more lines for Tom and Anne:

```text
Tom: How did I get here?
Anne: Oh, a writer put you here. This is a test conversation for Yarn Spinner!
Tom: What's Yarn Spinner?
Anne: Don't worry about it!
```

* And we'll make use of the variable we made earlier, to offer different lines depending on how it's set:

```text
<<if $knows_anne_name>>
    Tom: This is weird, Anne.
<<else>>
    Tom: This is really confusing.
<<endif>>
```

These lines use the `if` keyword, which allows you to check if a statement evaluates to true or not. When you write an `if` statement using the `if` keyword, the expressions is evaluated, and if it's true then the contents of the if statement are run.

In this case, if `$knows_anne_name` evaluates to true \(in other words, the variable has been set to true at some point earlier\) then Tom sys "This is weird, Anne" \(because he knows Anne's name\). 

If `$knows_anne_name` does not evaluate to true \(the variable has not been set to true at some point earlier, or has never been set to anything\) then Tom says "This is really confusing." \(and does not use Anne's name, because he doesn't know it yet!\)

* Add a few more lines to the end of the script:

```text
Anne: That's OK! This will all go away in a moment.
Tom: What?!
```

* Finally, add a call to a command named &lt;&lt;quit&gt;&gt;:

```text
<<quit>>
```

This command is not part of Yarn Spinner, but Yarn Spinner interprets anything between `<<` and `>>` as a command. We'll create a custom implementation for `<<quit>>` in Unity later on, so that the game knows what to do when this line is run.

* Save your script, and return to Unity.

