# Advanced Saliency

There have been several guides and samples about saliency and storylets in Yarn Spinner 3, so why not add one more! While previous samples have deliberately limited the amount of dynamic content, this sample explores what happens when you want highly dynamic content within the already dynamic nature of storylets themselves.

### What we'll be covering

* Dynamically building up Yarn content
* Dynamic selection of Yarn content
* Writing highly dynamic storylets
* Changing a scene on the fly in response to Yarn value changes
* Challenges in writing content for these types of games

### The Room

Unlike other samples, we need to provide some context before diving into how everything works. This sample demonstrates building a room where the characters, scenario, and even object layout are fully dynamic based on values set in Yarn. This approach is ideal for games where you have a team of characters accompanying the player or side-quests featuring previously encountered characters and locations, making the world feel more interconnected and responsive to player choices.

The structure for this sample includes four different scenarios: interrogation, exploration, rescue, or a date. Each scenario has two main non-player characters (primary and secondary), who can be any of four NPCs: Alice, Barry, George, or Liz. These scenarios can take place in one of four rooms: an office, pub, church, or mansion.

Even in this limited sample, there are up to **192 possible combinations** - far too many to write individually for just **four**different scenarios. The situation becomes worse when you consider that each scenario likely needs multiple nodes, creating an enormous writing burden.

As you add more scenarios, characters, and locations, the combinatorial explosion quickly outpaces even the fastest writers. To address this, we template the scenarios and use interpolation to inject different values into these templates. While replaying the same scenario repeatedly might reveal patterns, in a typical playthrough where each scenario is seen only once or twice, the game appears fully responsive to the player's actions.

This approach works particularly well for games with varied side quests that need to adapt to the player's situation. Games like Watch Dogs: Legion and Weird West use similar techniques to populate their worlds with highly reactive missions. While you could apply this approach to a main storyline, it's less common for a game's primary path since it sacrifices some of the control that's valuable for telling a specific story.

Using interpolation and templated scenarios offers two additional benefits:

1. You can still write highly specific scenarios alongside templated ones. For instance, you could craft detailed content for Alice and Liz exploring a mansion without writing all 191 other combinations.
2. It facilitates easier scaling, allowing different writers to handle specific scenarios without interfering with others' work. More niche combinations can be assigned to writers who best understand those characters, enabling more straightforward assignment and scaling of writing tasks.

### The Sample

![The advanced saliency sample showing off an office based scenario](<../.gitbook/assets/01 (1).png>)

The sample consists of several components: an initial configuration area where you can speak with Capsley for an explanation and interact with four buttons to configure the room, and a main room where the scenarios play out.

#### The buttons

Each button updates a specific Yarn variable. These variables control who the primary character is (`$primary`), who the secondary character is (`$secondary`), what scenario will be played out (`$scenario`), and what room it will take place in (`$room`).

Walking onto a button triggers an update to the relevant variable that the button controls. This allows you to configure the scenario details, participants, and location.

#### The Void

In the distance lies "the void," where characters not needed for the current scenario wait. While these characters could be instantiated from prefabs, we originally designed the sample differently, requiring all characters to exist in the scene simultaneously. Although we later changed this approach, we found the notion of characters waiting on a distant island amusing, so we kept it.

#### The Level God

The level god (`LevelGod.cs`) handles loading room props and placing characters. It manages a collection of room layouts (defined as scriptable objects) that specify prop placement, level content, and character positions. When it's time to run a scenario, the level god checks the variable storage, reads the current scenario, and loads the appropriate room layout. It then positions characters according to the layout specifications.

In an actual game, room geometry would likely be part of the general level design rather than defined in a configuration file. However, you would still need configuration for different scenarios, such as character placement and required props. You'd need some version of a "level god" to interpret this configuration and handle runtime setup.

#### Capsley

Capsley is responsible for triggering the scenario. Speaking with Capsley runs the final setup code needed to load the scenario, after which the primary and secondary characters take over.

### The Yarn

This sample contains more dialogue and uses significantly more interpolation than typical Yarn scripts. There's one main file (`room.yarn`) that sets up variables, contains Capsley's dialogue, and all bouncer nodes. Each scenario has its own file (`room-Date.yarn`,`room-Exploration.yarn`,`room-Rescue.yarn`,`room-Interrogation.yarn`), and there's an additional file demonstrating how to implement specific variable combinations (`room-Explore-Mansion-Liz-Alice.yarn`) alongside more generic ones.

We've organized the dialogue into two main node groups: `Primary` and `Secondary`, corresponding to the specific characters in those roles. These are accessed via bouncer nodes that apply across the entire sample rather than on a per-scenario basis. For example, if Alice is the Primary character, her bouncer node would be:

```yarn
title: Alice
when: $primary == .Alice
---
<<jump Primary>>
===
```

#### Character Interpolation

Perhaps the most noticeable difference from typical Yarn files is how speaker names are handled. Usually in Yarn, you define your speaker with their name followed by a colon, but here the speaker names are interpolated values. This addresses the issue of not knowing which character will speak a line, only that it will be either the primary or secondary character.

```yarn
{$primary}: date time!
Player: Date Time!
{$secondary}: DATE TIME!
{$primary}: why are you here?!
```

When this Yarn code runs, the names of characters in the `$primary` and `$secondary` roles are interpolated into the lines. If Alice is Primary and Liz is Secondary, this would be equivalent to:

```yarn
Alice: date time!
Player: Date Time!
Liz: DATE TIME!
Alice: why are you here?!
```

This works because the enums have been given string backing values matching their character names.

#### The Whens

With two node groups (`Primary` and `Secondary`), we need substantial filtering to prevent inappropriate storylets from appearing. The scenario serves as the main filter for node groups. To maintain clarity, each scenario has its own file, and every node in that file begins with the same filtering when clause. Additional clauses then track progression through the scenario. For example, the first node in the interrogation scenario when talking to the primary character has this header:

```yarn
title: Primary
when: $scenario == .Interogation
when: $scenario_state == .NotStarted
```

This isn't the only possible approach, but it's the most straightforward without requiring extensive custom code or limiting expressiveness. These combinations can become arbitrarily complex to accommodate highly specific situations:

```yarn
title: Primary
when: $scenario == .Explore
when: $Room == .Mansion
when: $primary == .Alice || $primary == .Liz
when: $secondary == .Alice || $secondary == .Liz
when: $scenario_state == .Started
when: $speak_to_secondary == false
```

These when clauses specify a scenario that's an exploration in a mansion with Alice and Liz as the main characters, where the scenario has started but the player hasn't spoken to the secondary character yet. While highly specific, breaking it into smaller pieces makes each condition manageable and understandable.

### Sample Limitations

Unlike most samples intended as starting points for implementing Yarn Spinner features, this sample has limitations. Although it demonstrates a working approach to advanced, dynamic story saliency, it's more restricted than what you'd want in a full game. These limitations primarily exist to keep the sample approachable as a starting point.

As you use storylets more extensively, their structure will increasingly reflect your game's needs. Even this relatively simple sample mirrors the structure of its scene: the story is told by two characters following a consistent progression through the scenario because that's all the sample supports. While this sample provides a good starting point for thinking about these concepts, you'll need to make decisions about storylet structure, information access, and flow in your own implementation.

The progression options here are deliberately limited to keep the sample manageable. Progression follows a single path, which would be too restrictive for a full game. Each scenario in a real game would need its own progression system and a way to easily query its state, likely through a custom function.

The writing approach used for storylets and character name interpolation works adequately but can become tedious in larger projects. Writing `{$primary}:` and `{$secondary}:` at the start of lines is functional but potentially frustrating over time. In a larger project, you might want to use a dedicated line provider or custom view code to simplify this, allowing for something like:

```yarn
A: date time!
Player: Date Time!
B: DATE TIME!
A: why are you here?!
```

While not a major improvement, this simplification adds up as your game scales.

Related to this is localization, which becomes considerably more challenging with heavy use of interpolation. The most important consideration is ensuring interpolated values undergo localization. In English, structures like `The {$room} is on fire` work without issue, but in languages where articles must agree with nouns, separating them causes problems. You'll likely need to process values through a localization function before injecting them rather than using direct interpolation.

Finally, we've overlooked how storylets are selected. A real game would need some form of drama manager to read the game state and configure scenarios appropriately. In this sample, we've simplified this with four buttons that act as a drama manager - understandable but not viable for a shipping game. Similarly, we use bouncer nodes to avoid rewriting dialogue interaction code, but in a larger project, it would make more sense to update each character to load the appropriate node group directly rather than bouncing through empty nodes.
