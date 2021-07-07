---
description: >-
  This example project demonstrates making a simple dialogue-based game when
  beginning with some character and location assets.
---

# 📝 Example Project 2

## Goals

1. Display Yarn dialogue in a Unity scene
2. Allow a player to select between options to respond
3. Use Yarn Spinner to trigger commands that change the scene, camera and characters

## Materials

* Yarn Spinner installed in Unity
* Yarn Spinner set up in a text editor
* **Starter Asset Package** downloaded and unzipped

## Instructions

Open a new Unity 3D project. Ensure Yarn Spinner has been added to the project in the Package Manager as per the [**Installation Instructions**](installation-and-setup.md).

![](../.gitbook/assets/screen-shot-2021-07-05-at-12.59.13-pm.png)

Drag the provided Asset Package into the **Project Window** where project files are displayed in Unity to import them into the project.

![The provided assets are being imported](../.gitbook/assets/screen-shot-2021-07-07-at-2.32.57-pm.png)

To see the **Scene** containing the imported assets, you'll need to open it. In the **Project Window**, navigate to **Assets &gt; Scenes** and select **SpaceJourney.unity**.

This package comes with four main things: 

1. character models for three different humans in spacesuits, 
2. a simple environment styled like the inside of a spaceship, 
3. some UI layers that always appear in front of the camera, and 
4. some basic C\# utility scripts that will be covered in more detail shortly.

The important part to know is that in the **Scene** there are a number of named but invisible markers—**GameObjects** with no model attached—that just store a location and a facing. These will be used as anchors to move other models around by sending them to markers based on name.

![](../.gitbook/assets/spaceship.png)

You can see these yourself in Unity by selecting each marker in **Location Markers** and allocating them an Icon using the dropdown at the top of the **Inspector**. The markers named `Camera` are the camera markers and the ones named like `Left` or `Right` are character markers.

![Camera markers have been assigned &#x1F536; icons and character markers &#x1F535; icons](../.gitbook/assets/screen-shot-2021-07-07-at-2.52.47-pm.png)

### Creating a Runnable Script

{% hint style="success" %}
The next step is to import the Dialogue System and hook up a Yarn Project and Yarn Script. If you have completed [**Example Project 1**](example-project-1.md) before, you may skip ahead to **Planning a Story**. Otherwise, let's proceed!
{% endhint %}

Yarn Spinner for Unity comes with a pre-made UI layer and accompanying utility scripts to handle displaying lines and presenting options from Yarn files. In the **Project Window** again, navigate to **Packages &gt; Yarn Spinner &gt; Prefabs** and drag **Dialogue System.prefab** into the scene.

![The Dialogue System has been added from the Project Window into the Scene](../.gitbook/assets/screen-shot-2021-07-07-at-2.55.18-pm.png)

When the **Dialogue System** in the scene is selected, the **Inspector** will display the Yarn Project it is expecting line from. Here, a **Yarn Project** is a kind of linking file that groups Yarn script files together. To make one, navigate to a sensible place for the file to live \(such as **Assets &gt; Dialogue**\) and right-click the **Project Window** pane to select **Create &gt; Yarn Spinner &gt; Yarn Project**.

{% hint style="info" %}
The existence of Yarn Projects allows larger games with multiple dialogue systems \(e.g. main story dialogue, barks, storylets\) to separate into multiple projects that pass lines to different UI or systems. This allows an extra level of organisation above separate Yarn files which are typically used to separate story scenes or parts.

However, most games will need only a single Yarn Project.
{% endhint %}

Select the scene's **Dialogue System** again and drag the new **Yarn Project** into the labelled slot in the **Inspector**.

![The new Yarn Project has been added to the Dialogue System&apos;s Dialogue Runner](../.gitbook/assets/screen-shot-2021-07-07-at-2.58.16-pm.png)

Now the Yarn Project needs one or more **Yarn Scripts** to get dialogue from. Just like with the Yarn Project, navigate to the desired file location and select **Create &gt; Yarn Spinner &gt; Yarn Script**. Then, with the Yarn Project selected, drag the newly created script into the Inspector slot labelled **Source Scripts**. Click **Apply**.

![The new Yarn Script has been added to the Yarn Project&apos;s Source Scripts](../.gitbook/assets/screen-shot-2021-07-07-at-2.59.17-pm.png)

### Filling Out your Script

By default, a new Yarn Script begins with a single empty node with the name of the file. Open the file, rename the node to **Start** and put a single line of test dialogue. You may remove the `tags` field.

```text
title: Start
---
This is a line of test dialogue.
===
```

Returning to Unity, pressing the ▶️ button results in the test line being displayed in front of the empty scene world. Pressing **Continue** will make the UI disappear, as it has reached the end of the script. If you do not see this, read onward for a common fix.

![The test line from the Yarn Script has been displayed in the otherwise empty game](../.gitbook/assets/screen-shot-2021-07-07-at-3.02.18-pm.png)

{% hint style="danger" %}
If you only see a black screen, the included fade-to-black layer is turned on and blocking the camera from seeing the scene. Hide this by selecting **UI Layers** from the **Scene Hierarchy** and unchecking the box at the top of the **Inspector**.
{% endhint %}

![The Title Layer and Fade Layer objects have been hidden from the Scene](../.gitbook/assets/screen-shot-2021-07-07-at-3.01.31-pm.png)

It's time to plan a story. In this Asset Package there are three character models called **Engineer**, **Crewmate** and **Captain**.

![](../.gitbook/assets/characters.png)

These low-poly spacefarers live and work on a spaceship with the player. It's a new day on the job in Space Fleet, the player is in the corridor and the must decide which of their three shipmates they're going to speak to. The choices presented are:

* The **Engineer**, who will complain to the player about his job.
* The **Crewmate**, who the player will attempt to convince should give them extra rations.
* The **Captain**, who will try to judge whether the player is ready for action.

After a short conversation with the chosen character, a shipwide alert requests all hands report to the bridge. When the player arrives, the **Captain** reveals that space pirates are attacking. The one of two things happens:

1. If the player chose to speak to the **Captain** earlier, and **succeeded** in convincing her that they were ready for action, the player is sent to fight off the pirates and save the day.
2. If the player either didn't speak to the **Captain**, or **failed** to convince her that they were ready for action, the **Crewmate** is sent instead.

This short story provides an initial choice between three paths, and results in the player achieving one of two endings. A tree representation of the story would look as follows:

![](../.gitbook/assets/tree.png)

So it's time for the actual writing part. Here, I've opened my new Yarn Script in **Visual Studio Code** with the **Yarn Spinner Extension** installed as per the [**Installation Instructions**](../getting-started/installation-and-setup.md). I've written a minimal script that follows the planned story, as a skeleton that can be expanded on later.

![The new Yarn Script has been given some simple content](../.gitbook/assets/screen-shot-2021-07-06-at-2.49.01-pm.png)

You can find this example script below to copy. Or if you want to make you own version and need a refresher on how to represent it in Yarn, refer to the [**Syntax and File Structure guide**](../getting-started/yarn-syntax-and-file-structure-1/). 

```text
title: Start
---
Player: Another day in Space Fleet. Might go have a chat...
// pick a person to speak to
-> Go see the Engineer as per orders
    <<jump TalkToEngineer>>
-> Meet up with your friend
    <<jump TalkToCrewmate>>
-> Go and talk to the Captain
    <<jump TalkToCaptain>>
===
title: TalkToEngineer
---
Engineer: Hello! I am the Engineer.
<<jump BridgeEnding>>
===
title: TalkToCrewmate
---
Crewmate: Hello! I am your Crewmate.
<<jump BridgeEnding>>
===
title: TalkToCaptain
---
Captain: Hello! I am the Captain.
Player: I want to talk to go on more missions.
Captain: Do you think you are ready?
-> Yes
    <<set $away_mission_readiness += 1>>
    // if so, ask again
    Captain: Really?
    -> ...yes?
        <<set $away_mission_readiness += 1>>
    -> Actually, no.
-> No
// now go to the ending
<<jump BridgeEnding>>
===
title: BridgeEnding
---
// everyone reports to the bridge
Captain: Pirates!
Player: Oh no!
// now change who goes depending on player actions
<<if $away_mission_readiness < 2>>
    Captain: Crewmate, go deal with those pirates!
    Crewmate: Yes, Captain.
<<else>>
    Captain: Player, you were just telling me how ready for this you are. 
    Captain: Go deal with those pirates!
    Player: Hooray!
<<endif>>
===
```

Once you've got a basic story, pop back into Unity and check the basics:

* [x] Lines display correctly
* [x] Pressing **Continue** advances lines correctly
* [x] Selecting different options have the expected outcomes

![The Yarn Script content is displaying lines, advancing lines and selecting options correctly](../.gitbook/assets/screen-shot-2021-07-07-at-3.09.04-pm.png)

### Adding Commands

Speaking to an empty void is all well and good, but this particular game is going to be more compelling if it makes use of the provided assets to make dynamic visuals. To empower our Yarn script to invoke changes in Unity, we'll need to make some **Commands**. For this project, we'll make commands to:

* **Move the Camera** to preset locations, as if the player is moving.
* **Turn on and off UI elements**, to create nice transitions during Scene changes.
* **Move Character models** to preset locations, as if they are entering and exiting the Scene.
* **Change Character model animations and textures**, as if they are showing different emotions.

The first three will need to exist throughout the Scene, while the last should attach to specific **Character** objects so each can be controlled independently. The code to do each of these things is already written in provided C\# scripts, so we just need to create commands that make the functionality availabe to Yarn scripts in the project.

#### Scene-Wide Commands

Code for the scene-wide commands are included in **Assets &gt; Scripts &gt; SceneConductor.cs**. To make functions from the script available throughout the project, it is attached to an otherwise empty **GameObject** in the Scene called **SceneConductor**.

With our first command we want to be able to be able to move the Scene's Main Camera to an invisible marker in the Scene with the given name. The function from **VisualNovel.cs** that we want to be able to invoke from Yarn is called `MoveCamera()` and it looks like this:

```csharp
// moves camera to camera location {location}>Camera in the scene
private void MoveCamera(string locationName) {
    Transform destination = GetLocationMarkerWithName(locationName, "Camera");
    MoveTransform(Camera.main.transform, destination);
}
```

It takes the name of a marker that has been tagged as a **Location** in the Scene, from the available markers **Title**, **Corridor** and **Bridge**. ****It then finds the location and facing of the marker named **Camera** in that **Location** and sets the camera location and facing to that of the marker. If the camera moves to the **Title** location, the **Title Layer** element will fill the screen and appear as if a splash screen was being shown. If moved to the **Corridor** or **Bridge** locations, it acts as the point of view of the player who is then seen to be currently in that location. The default camera location is **Title**.

Here, we want to make a Yarn command called `camera` that takes a location name and knows to pass it off to the `MoveCamera()` function to make it happen. This will mean when the player has to move to the bridge, the Yarn script can just say `<<camera Bridge>>`.

Making a command that can then be used in Yarn is as simple as registering a **Command Handler**. A Command Handler tells the **Dialogue System** that a Yarn command exists with a given name, how many additional pieces of information it needs, and which C\# function to pass this information to when it's called. Then, when the game runs, the Dialogue System will handle talking to C\# for you.

Command Handlers have two important requirements:

1. They must be created before the command can ever be called. Usually, this means you want to make it as part of the initial creation of the scene or the object it's attached to. 
2. They must be attached to the Dialogue System's **Dialogue Runner** object. It's the thing passing lines of dialogue to the scene that has to know to change behaviour if the next line it receives is a command instead of dialogue.

To satisfy the first point, we can register any Command Handlers in a function called `Awake()` that every Unity object has by default. This function is called when the object is created, and because our empty **Scene Conductor** object is always in the Scene this means it gets created as soon as the Scene does. Registering Command Handlers in the `Awake()` function of this object therefore means they will be registered before anything else happens when the game is run.

To satisfy the second, we need to find the **Dialogue Runner** in the scene and assign it to a variable in C\# that we can then attach Command Handlers to. Because there is only one Dialogue Runner in the Scene, we can find it by asking Unity to give us all the objects in can find in the Scene of type DialogueRunner. 

Altogether, this means two simple lines in the `Awake()` function of **VisualNovel.cs**:

```csharp
// find the Dialogue Runner
dialogueRunner = FindObjectOfType<Yarn.Unity.DialogueRunner>();
// register Command Handler for <<camera NAME_OF_LOCATION>>
dialogueRunner.AddCommandHandler<string>("camera", MoveCamera);
```

Return to the Yarn script and add `<<camera Corridor>>` to the top of the **Start** node, and `<<camera Bridge>>` to the top of the node where characters should move to the bridge. To show the title before the game begins, add `<<camera Title>>` and then a call to the `wait` command that Yarn comes with automatically, so the camera doesn't cut away before the title can be seen.

{% hint style="warning" %}
If you hid the **Title Layer** object earlier, be sure to unhide it now by selecting it and re-ticking the box at the top of the **Inspector**. If necessary, unhide **UI Layers** and re-hide just the **Fade Layer**.
{% endhint %}

These minimal changes to the Yarn script...

```text
title: Start
---
<<camera Title>>
<<wait 2>> // hold for 2 seconds before changing
<<camera Corridor>>
// ... [lines omitted]
===
title: BridgeEnding
---
// everyone reports to the bridge
<<camera Bridge>>
// ... [lines omitted]
===
```

...should now result in the camera moving around the empty environment in the appropriate points in the script. Returning to Unity, press the ▶️ button and playthrough to check this works correctly.

![The camera now moves around the scene as commands are reached in the Yarn script](../.gitbook/assets/screen-shot-2021-07-07-at-4.23.03-pm.png)

Onto the next command! Smash cuts are fine, but nice transitions are fancier. In the Scene there is a flat black layer called **Fade Layer** that sits in front of the camera. Changing its opacity can make the camera appear to fade to and from black. Back in **SceneConductor.cs** there is a line in the `Awake()` function that finds the objects of type **Fade** **Layer** in the Scene \(there is only the one\) and keeps it in a variable called `fadeLayer`, similar to how the **Dialogue Runner** was found earlier.

```csharp
// find the Fade Layer
fadeLayer = FindObjectOfType<FadeLayer>();
```

Then further down the file there are short functions called `FadeIn()` and `FadeOut()` that do just that, by changing the opacity of this stored layer over the given number of seconds \(or defaulting to **1** second if no argument is provided\).

```csharp
// fades in a black screen over {time} seconds
private Coroutine FadeIn(float time = 1f) {
    return StartCoroutine(fadeLayer.ChangeAlphaOverTime(0, time));
}

// fades out a black screen over {time} seconds
private Coroutine FadeOut(float time = 1f) {
    return StartCoroutine(fadeLayer.ChangeAlphaOverTime(1, time));
}
```

These functions are a little different in that instead of returning nothing like the `MoveCamera()` function did, these functions return a `Coroutine`. This gives Yarn Spinner a handle to the process it triggered so that for operations that take time \(like fading in a screen over a second or so\) it knows not to trigger the next line of dialogue until this process has completed.

Again, the functionality that performs the actual opacity change is contained in a C\# script attached to the relevant GameObject. In this case it is a file called **FadeLayer.cs** attached to the **Fade Layer**. 

Adding commands for `fadeIn` and `fadeOut` works just like before. In the `Awake()` function of **SceneConductor.cs** by adding **Command Handlers** to the previously found **Dialogue Runner.**

```csharp
// Handlers for <<fadeIn DURATION>> and <<fadeOut DURATION>>
dialogueRunner.AddCommandHandler<float>("fadeIn", FadeIn);
dialogueRunner.AddCommandHandler<float>("fadeOut", FadeOut);
```

Back in the Yarn script, adding a `<<fadeOut>>` and `<<fadeIn>>` to either side of each camera or node change will make nice fade-to-black transitions between story parts. Because no argument is provided, this will perform a 1 second fade.

{% hint style="info" %}
Including transitions between conversation nodes even if they occur in the same Corridor location will hide the characters appearing that will be implemented next.
{% endhint %}

![A black overlay fades in and out to cover camera move transitions](../.gitbook/assets/screen.gif)

All this took is a few more additions to the Yarn script:

```text
title: Start
---
<<fadeIn>>
<<camera Title>>
<<wait 2>> // hold for 2 seconds before changing
<<fadeOut>>
<<camera Corridor>>
<<fadeIn>>
// ... [lines omitted]
===
title: TalkToEngineer
---
<<fadeOut>>
<<fadeIn>>
// ... [lines omitted]
===
title: TalkToCrewmate
---
<<fadeOut>>
<<fadeIn>>
// ... [lines omitted]
===
title: TalkToCaptain
---
<<fadeOut>>
<<fadeIn>>
// ... [lines omitted]
===
title: BridgeEnding
---
<<fadeOut>>
// everyone reports to the bridge
<<camera Bridge>>
<<fadeIn>>
// ... [lines omitted]
<<fadeOut>>
===
```

The next command will allow character models to be placed in the Scene whenever they are part of the current conversation. In our example nobody ever leaves a location while the player is still there, so there's no need for the opposite. We could just as easily have attached this code to each individual **Character** but by putting it in **SceneConductor.cs** we can make use of the same functions that find Location markers as used in the `MoveCamera()` function.

In **SceneConductor.cs** there is a function called `MoveCharacter()` that accepts a `Character` object and strings for the Location and marker names. When Yarn script need to pass an argument of a project-specific type \(like `Character` is\) it simply searches the scene for objects of that type with the given name.

```csharp
// moves character named {characterName} to location 
// {locationName}>{markerName} in the scene
private void MoveCharacter(Character char, string locationName, string markerName) {
    Transform destination = GetLocationMarkerWithName(locationName, markerName);
    MoveTransform(character.transform, destination);
}
```

## Result

A playable visual novel-type game with multiple characters and scenes and sensible transitions between them.

