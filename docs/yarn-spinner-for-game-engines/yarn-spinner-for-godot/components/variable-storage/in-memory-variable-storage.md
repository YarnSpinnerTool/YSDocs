# In-Memory Variable Storage

The In-Memory Variable Storage component is a Variable Storage component that stores all variables in memory. These variables are erased when the game stops.

{% hint style="info" %}
The In-Memory Variable Storage component is intended to be a useful tool for getting started, and to be replaced with a custom variable storage that meets your game's needs. 

However, if your game has no need to save and restore game state, then this class can be used in your final game, too.
{% endhint %}

### Inspector

|Property|Description|
|---|---|
|Debug Text View|<p>A RichTextLabel node that will display a summary of the variables that have been stored in this component. If this is not set, this property will not be used.</p><p>You can use this property to display a debug summary of your variables at run-time in your games.</p>|
