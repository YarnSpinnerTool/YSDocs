# Markup

Markup allows you to add attributes into your text, like `[a]hello[/a]`. These attributes can be used by your game to do things like change the formatting of the text, add animations, and more.

When text is parsed, the tags are removed from the text, and you receive information about the range of the plain text that the attributes apply to.

## Attributes

Attributes apply to ranges of text:

```yarn
Oh, [wave]hello[/wave] there!
```

Yarn Spinner will take this text, and produce two things: the _plain text_, and a collection of _attributes_. The plain text is the text without any markers; in this example it will be:

```yarn
Oh, hello there!
```

Attributes represent ranges of the plain text that have additional information. They contain a _position_, a _length_, and their _name_, as well as their _properties_.

In this example, a single attribute will be generated, with a position of 4, a length of 5, and a name of "wave".

Attributes are opened like `[this]`, and closed like `[/this]`.

### Overlapping Attributes

Attributes can overlap:

You can put multiple attributes inside each other. For example:

```yarn
Oh, [wave]hello [bounce]there![/bounce][/wave]
```

You can close an attribute in any order you like. For example, this has the same meaning as the previous example:

```yarn
Oh, [wave]hello [bounce]there![/wave][/bounce]
```

### Self-closing Attributes

Attributes can self-close:

```yarn
[wave/]
```

A self-closing attribute has a length of zero.

### The Close-All Marker

The marker `[/]` is the _close-all_ marker. It closes all currently open attributes. For example:

```yarn
[wave][bounce]Hello![/]
```

### Properties

Attributes can have properties:

```yarn
[wave size=2]Wavy![/wave]
```

This attribute 'wave' has a property called 'size', which has an integer value of 5.

### Short-hand Properties

Attributes can have short-hand properies, like so:

```yarn
[wave=2]Wavy![/wave]
```

This is the same as saying this:

```yarn
[wave wave=2]Wavy![/wave]
```

This attribute 'wave' has a property called 'wave', which has an integer value of 2. The name of the attribute is taken from the first property.

### Property Types

Properties can be any of the following types:

- Integers
- Floats
- 'true' or 'false'
- Strings

Single words without quote marks are parsed as strings. For example, the two following lines are identical:

```yarn
[mood=angry]Grr![/mood]
[mood="angry"]Grr![/mood]
```

### Whitespace Trimming

If a self-closing attribute has white-space before it, or it's at the start of the line, then it will trim a single whitespace after it. This means that the following text produces a plain text of "A B":

```yarn
A [wave/] B
```

{% hint style="info %}

If you don't want to trim whitespace, add a property `trimwhitespace`, set to `false`:

```yarn
A [wave trimwhitespace=false/] B 
// (produces "A  B")
```

{% endhint %}

## Showing Special Characters to the Player

You may want to show text containing the `[` and `]` characters to your player. To prevent the markup parser from treating as special characters, you can *escape* them. Text that has been escaped will be treated as plain text, and will not be interpreted by the parser.

There are two ways to escape your markup: escaping single characters, and using the `nomarkup` attribute.

### Escaping single `[` and `]` characters

If you need to escape a single square bracket character, put a backslash `\` in front of it:

```yarn
Here's some square brackets, just for you: \[ \]
```

This will appear to the player as:

```
Here's some square brackets, just for you: [ ]
```

The backslash will not appear in the text.

{% hint style="info %}
If you need to show a blackslash in your text, use two blackslashes:

```yarn
Here's a backslash! \\
```

This will appear as:

```yarn
Here's a backslash! \
```
{% endhint %}

### The `nomarkup` Attribute

If you want to escape a longer run of text, or if you have many square brackets, escaping a single character at a time can be cumbersome. In these cases, you may want to escape an entire region of text, using the `nomarkup` attribute. This attribute makes the parser ignore any markup characters inside it.

If you want to include characters like `[` and `]`, wrap them in the `nomarkup` attribute:

```yarn
[nomarkup]Here's a big ol' [ bunch of ] characters, filled [[]] with square [[] brackets![/nomarkup]
```

This will appear as:

```
Here's a big ol' [ bunch of ] characters, filled [[]] with square [[] brackets!
```

## The `character` Attribute

The `character` attribute is used to mark the part of the line that identifies the character that's speaking. 

Yarn Spinner will attempt to add this character for you, by looking for character names in lines that look like this:

```yarn
CharacterA: Hello!
CharacterB: Oh, hi!
```

The markup parser will mark everything from the start of the line up to the first `:` (and any trailing whitespace after it) with the `character` attribute. This attribute has a property, `name`, which contains the text from the start of the line up to the `:`. If a `:` isn't present, or a `character` attribute has been added in markup, it won't be added.

This means that the example above is treated the same as this:

```yarn
[character name="CharacterA"]CharacterA: [/character]Hello!
[character name="CharacterB"]CharacterB: [/character]Oh hi!
```

You can use this to trim out the character names from lines in your game.

## Text Replacement Markers

Certain attributes in Yarn Spinner's markup are "replacement" markers, which Yarn Spinner uses to insert or replace text based on the value of a variable. There are three built-in replacement markers:

* The `select` marker uses the value of a variable to choose an outcome.
* The `plural` marker uses the value of a number to decide on the *plural class* for that number.
* The `ordinal` marker uses the value of a number to decide on the *ordinal class* for that number.

All three of these markers have a property called `value`, and use this to decide what text should be used in the line.

### `select`

The `select` marker is the simplest of the built-in replacement markers. It takes the value of the `value` property, and uses that to choose a replacement.

It's especially useful for when you need to insert a gendered pronoun in a line:

```yarn
// In this example, the $gender variable is a string that
// contains either "m", "f", or "nb".

I think [select value={$gender} m="he" f="she" nb="they" /] will be there!

// Depending on the value of $gender, this line can appear
// as one of these possible options:
I think he will be there!

// or:
I think she will be there!

// or:
I think they will be there!
```

### `plural` and `ordinal`

The `plural` and `ordinal` markers take a number in its `value` property, and use that to determine the plural or ordinal number class of that value.

#### Plurals across different languages

Different languages have different rules for how numbers are pluralised. 

In many languages, the term you use to refer to a thing depends on the the number of that thing. This is known as a *plural class*: in English, you can have one *apple*, but many *apples*, and you have have one *mouse*, but many *mice*.

However, the rules vary significantly across different languages. English has two: "single", and "other". However, for example, Polish has multiple. 

* In English, you say "one apple, two apples, five apples".
* In Polish, you say "jedno jabłko, dwa jabłka, pięć jabłek".
 
Notice how the Polish word for "apple", "jabłko", takes multiple forms as the number changes, whereas it takes two forms in English.

In Yarn Spinner, individual lines are replaced depending on the user's locale, but the logic surround them is not. This means that, if you want to be able to translate your game into multiple languages, you can't write Yarn code like this:

```
<<if $apple_count == 1>>
    You have one apple!
<<else>>
    You have {$apple_count} apples!
<<endif>>
```

If you did it this way, the logic would only work for languages that have the same rules for plurals as English. (There are several of them that do, but far more that don't.)

Complicating this further, there are two main kinds of plural classes: *cardinal* plural classes, and *ordinal* plural classes. 

* Cardinal plural classes are the kind we just saw (for example, "one apple, two apples"). 
* Ordinal plural classes refer to the positioning of a thing; in English, ordinal numbers are things like "1st, 2nd, 3rd." 

As with cardinal plural classes, different languages have different ordinal plural classes.

#### Pluralising with `plural` and `ordinal`

Yarn Spinner is able to take a number and the user's current locale, and determine the correct cardinal or ordinal plural class of that number, for that locale. You can then use the plural class to decide on what text to show.

`plural` and `ordinal` have a property called `value`, just like `select`. They then have a property for each of the current locale's plural classes. These can be:

* `one`
* `two`
* `few`
* `many`
* `other`

The two markers differ based on what kind of plural class they work with:

* `plural` selects a number's *cardinal* plural class.
* `ordinal` selects a number's *ordinal* plural class.

Not every language uses every category; for example, English only uses "one" and "other" for cardinal plural classes.

For each of these properties, you provide the text that should appear. 

For example:

```yarn
PieMaker: Hey, look! [plural value={$pie_count} one="A pie" other="Some pies" /]!

// This will appear as either:
PieMaker: Hey, look! A pie!

// or: 
PieMaker: Hey, look! Some pies!
```

You can include the actual value in the resulting text by using the `%` character. This character will be replaced with the value provided to the `value` property:

```yarn
PieMaker: I just baked [plural value={$pie_count} one="a pie" other="% pies" /]!

// This will appear as, for example:
PieMaker: I just baked a pie!"

// or:
PieMaker: I just baked 4 pies!"
```

The `ordinal` marker works similarly, but uses the ordinal plural class:

```yarn
Runner: The race is over! I came in [ordinal value={$race_position} one="%st" two="%nd" few="%rd" other="%th" /] place!

// This will appear as, for example:
Runner: The race is over! I came in 1st place!

// or:
Runner: The race is over! I came in 23rd place!
```