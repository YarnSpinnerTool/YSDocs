---
description: Learn about using Commands in Yarn Spinner.
icon: chevrons-left
---

# Commands

In Yarn Spinner, you can send instructions to your game through **commands**. Commands look like this:

```yaml
<<wait 2>>
<<setsprite ShipName happy>>
<<fade_out 1.5>>
```

Commands are sent to your game's [Dialogue Runner](../../yarn-spinner-for-unity/components/dialogue-runner.md), just like lines and options are. Commands are not shown to the player directly; instead, they're used for things like stage directions.

Yarn Spinner comes with some **built-in commands**; however, to get the most usefulness out of them, you'll want to [define your own custom commands](../../yarn-spinner-for-unity/creating-commands-functions.md) that make your game do what you need to.

## Built-in Commands

There are two built-in commands in Yarn Spinner: `wait`, and `stop`.

### `wait`

The `wait` command pauses the dialogue for a specified number of seconds, and then resumes. You can use integers (whole numbers), or decimals.

```yaml
// Wait for 2 seconds
<<wait 2>>

// Wait for half a second
<<wait 0.5>>
```

### `stop`

The `stop` command immediately ends the dialogue, as though the game had reached the end of a node. Use this if you need to leave a conversation in the middle of an `if` statement, or a shortcut option.

```yaml
// Leave the dialogue now
<<stop>>

// Leave the dialogue if we don't have enough money
<<if $money < 50>>
    Shopkeeper: You can't afford my pies!
    <<stop>>
<<endif>>
```

## Making Your Own Commands

You can create your own commands, so that your scripts can send directions to your game. For more information on how to create them in Unity games, see [Creating Commands and Functions](../../yarn-spinner-for-unity/creating-commands-functions.md), in the Yarn Spinner for Unity section of the documentation, and equivalents for other engines.

{% hint style="danger" %}
We recommend that you only move into the Yarn Spinner for Unity documentation after learning the fundamentals of Yarn Spinner Scripting.
{% endhint %}
