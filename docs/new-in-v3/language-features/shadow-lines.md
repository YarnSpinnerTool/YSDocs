---
description: Learn about reusing the same line in multiple places, using shadow lines.
---

# Shadow Lines

In Yarn Spinner 3, shadow lines let you reuse the same line in multiple places, without having to create duplicate copies.&#x20;

{% hint style="info" %}
Shadow lines are copies of other lines, but don’t create a duplicate entry in the string table. This can be useful if you want to re-use an existing line in more than one place, which can be important when each line has in-game assets like voice-over recording.
{% endhint %}

Shadow lines are marked using the `#shadow:` hashtag. When you use the `#shadow:` tag, you specify the line ID of another line, which is called the source line. The source line must have an explicit `#line:` hashtag to identify it.

Here’s a simple example of using shadow lines:

```
title: Tavern
---
Ava: Hello, barkeep!  
Guy: Hi there, how can I help? 
Ava: I should go. #line:departure
===

title: Kitchen
---
Ava: Greetings, chef!
Guy: What are you doing back here? 
Ava: I should go. #shadow:departure
===
```

The script contains six lines, but only 5 string table entries will be created, because the line _“I should go”_ is shadowed.

Shadow lines are required to have the same text in the Yarn script as their source line, but are allowed to have different hashtags (in addition to the `#shadow:` and `#line:` hashtags).
