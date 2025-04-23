---
description: Learn about using smart variables that determine their value at run-time.
icon: binary-circle-check
---

# Smart Variables

**Smart variables** in Yarn Spinner are a powerful way to improve your dialogue and narrative flows. Unlike regular variables that only change when explicitly set, smart variables recalculate their value every time they're accessed, based on the expression that defines them.

### Why Use Smart Variables?

1. **Code Readability**: They make your dialogue scripts more readable by using meaningful names instead of complex conditions.
2. **Centralised Logic**: Define a condition once and use it throughout your game.
3. **Maintenance**: When game mechanics change, you only need to update the smart variable declaration, not every place it's used.
4. **Abstraction**: They hide complex game state checks behind simple, descriptive names.

### Practical Examples

Creating a smart variable in Yarn Spinner is straightforward: `<<declare>>` command followed by a variable name (with the `$` prefix) and assign it an [expression](./#variables-and-expressions) rather than a static value. The expression can use [mathematical operations, logical comparisons](./#operators), or even reference other variables.&#x20;

For example: `<<declare $is_powerful = $strength > 50 && $magic_ability >= 20>>`. This smart variable will automatically update whenever the values of `$strength` or `$magic_ability` change, making your dialogue able to dynamically respond to the player's stats without additional code.

#### Example 1: Character Relationships

```markup
<<declare $player_is_friends_with_sam = $sam_relationship_score > 50>>

<<if $player_is_friends_with_sam>>
  Sam: Hey buddy! Good to see you again.
<<else>>
  Sam: Oh, it's you. What do you want?
<<endif>>
```

#### Example 2: Item Availability

```markup
<<declare $has_enough_materials = $wood >= 5 && $nails >= 10>>
<<declare $has_required_skill = $carpentry_level >= 3>>
<<declare $can_build_chair = $has_enough_materials && $has_required_skill>>

<<if $can_build_chair>>
  Craftsman: You've got everything you need to build that chair now.
<<else>>
  <<if !$has_enough_materials>>
    Craftsman: You'll need more materials first.
  <<else>>
    Craftsman: Your carpentry skills aren't quite there yet.
  <<endif>>
<<endif>>
```

#### Example 3: Time-Based Events

```markup
<<declare $is_evening = $game_hour >= 18 && $game_hour < 22>>
<<declare $town_shops_open = !$is_holiday && $game_hour >= 9 && $game_hour < 18>>

<<if $is_evening && !$town_shops_open>>
  Innkeeper: Most shops are closed now, but you're welcome to stay here for the night.
<<endif>>
```

### Benefits in Complex Games

Smart variables shine when you have conditions that you check frequently or that combine multiple factors. They're especially useful for:

* Tracking complex character states
* Monitoring game world conditions
* Representing player achievements or quest status
* Creating dynamic dialogue that responds to multiple game systems

By using smart variables, you make your dialogue scripts more intuitive and maintainable while keeping your game logic organised.
