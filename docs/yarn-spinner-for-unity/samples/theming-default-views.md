# Theming Default Views

The default presenters that come with Yarn Spinner have their own specific look, but they're designed to be rethemed without requiring any custom code. This tutorial demonstrates how to modify the built-in line and options presenters to use a sliced sprite and different font for a complete visual overhaul—all without writing _any_ code.

![Our rethemed line presenter](<../../.gitbook/assets/01 (3).png>)

### What we'll be covering

* Modifying existing dialogue presenters
* Slicing sprites via the sprite editor
* Importing custom fonts into TextMeshPro
* The nightmare hellscape that is Unity UI

If you want to see a finished version of this project, you can find it at **PATH TO SAMPLE**.

### Building the scene

If you haven't already installed Yarn Spinner, follow the instructions in the **link to install guide**. Once installed, we'll start by building out a basic scene:

1. Make a new scene in Unity.
2. From `Samples/Shared Assets/Prefabs` drag the Basic Arena into the scene
3. From `Samples/Shared Assets/Prefabs` add a Camera Rig into the scene
4. From `Samples/Shared Assets/Prefabs` drag a Player prefab into the scene
5. From `Samples/Shared Assets/Prefabs` drag an NPC prefab into the scene and rename it to be `Alice`
6. Add a default dialogue system to the scene, in the Hierarchy right click `Yarn Spinner -> Dialogue Runner`
7. Create a new Yarn Spinner project `Assets -> Create -> Yarn Spinner -> Yarn Project` and name it `Rethemed Dialogue`
8. Create a new Yarn script `Assets -> Create -> Yarn Spinner -> Yarn Script` and name it `Alice`
9. Delete the previous camera called `Main Camera`

#### The Dialogue

Replace the contents of the Alice Yarn script with the following:

```yarn
title: Alice
---
Player: Hello
Alice: Hello, this is a sample showing off retheming the base dialogue presenters

-> Neat
    Alice: right?
-> Dull
    Alice: rude!
===
```

This is a very simple node with just a few lines of dialogue and a single option. All we need is to show off the main features of lines and options, so feel free to change it, but for now this is sufficient.

#### Configuring the scene

1. Select the Camera Rig and in the inspector drag the Player into the target field
2. Select Alice and in the Inspector set the Dialogue field to use the new `Rethemed Dialogue` project
3. Select Alice and in the Inspector select the Alice node in the dropdown
4. Select Alice and in the Dialogue Runner field drag in the Dialogue System object from the hierarchy
5. Select the Dialogue System and in the Inspector set the Yarn Project to use the `Rethemed Dialogue` project

### The Font

Arguably the easiest but most impactful change you can make is to use a different font. This will **immediately** make the UI look different with minimal effort. Selecting a font is a very important stylistic choice for your game, as it will influence **everything** about how you design the rest of your UI.

For this sample, we've chosen a pixel font that works well with our desired aesthetic. At this stage, we're just adding the font to the project; we'll connect it to the various presenters later.

1. Grab the PixelifySans font from **LINK TO FONT**
2. Add the font into the Project assets
3. Go to `Window -> TextMeshPro -> Font Asset Creator`
4. Drag the `PixelifySans-Bold` font into the Source Font field
5. Click `Generate Font Asset`
6. Click `Save` and save the TMP version of the font into your project
7. Repeat these steps for the `PixelifySans-Regular` font

With this done, our fonts are ready to be used. We'll return to them when we start making layout changes, but first we also need some sprites.

### The Sprites

Our retheming will rely on a sprite sheet that we'll slice. Let's set that up now. We'll need the Sprite Editor for slicing, which you might already have installed.

1. Open the Package Manager by going to `Window -> Package Manager`
2. In the side bar select the `Unity Registry` option
3. Wait for Unity to populate the manager
4. Find the package called `2D Sprite`
5. Install it

![The package manager showing off the now installed 2D Sprite package](<../../.gitbook/assets/02 (1) (1).png>)

6. Add the sprite sheet into the project from **link to sprite sheet**
7. Select the sprite sheet and in the Inspector change it's Texture Type to be `Sprite (2D and UI)`
8. Set the sprite mode to be `Multiple`
9. Set the Pixels per Unit to be `20`
10. Set the Filter Mode to be `Point (no filter)`
11. Click Apply
12. Select the sprite sheet and in the Inspector click on the `Open Sprite Editor` button

![The Sprite Editor showing our sprite sheet](<../../.gitbook/assets/03 (1) (1).png>)

Now we need to slice the sprite sheet into individual sprites and define the regions. Without doing this, the sprites would stretch in undesirable ways and look distorted. We need to identify and slice eight different sprites, which is somewhat tedious to describe, but thankfully the Sprite Editor makes the process relatively straightforward.

1. In the top bar of the editor, in the Slice dropdown configure it to be an `Automatic` slice with a `Center` pivot and click the `Slice` button

This does most of the work for us, using the transparent space in the sprite sheet to identify the eight different sprites. Now that we have the individual sprites identified, we need to define which regions can stretch and which cannot. Without this step, the sprites will scale oddly.

2. Select the left-topmost sprite
3. Name it `Button-Filled-Up`
4. Set it's L, R, T, and B to all be `7`
5. Select the sprite on the right of the `Button-Filled-Up` sprite
6. Name it `Button-Empty-Up`
7. Set it's L, R, T, and B to all be `7`
8. Select the sprite on the right of the `Button-Empty-Up` sprite
9. Name it `Button-Continue-Up`
10. Set it's L, R, T, and B to all be `7`
11. Select the sprite on the right of the `Button-Continue-Up` sprite
12. Name it `Option-Selected`
13. Select the sprite below the `Button-Filled-Up` sprite
14. Name it `Button-Filled-Down`
15. Set it's L, R, T, and B to all be `7`
16. Select the sprite on the right of the `Button-Filled-Down` sprite
17. Name it `Button-Empty-Down`
18. Set it's L, R, T, and B to all be `7`
19. Select the sprite on the right of the `Button-Empty-Down` sprite
20. Name it `Button-Continue-Down`
21. Select the bottom-leftmost sprite
22. Name it `Background`
23. Set it's L, R, T, and B to all be `16`
24. Click the Apply button

Now all our sprites are neatly sliced and ready to use. This was quite a bit of slicing, but fortunately most sprites use the same slice settings. If you don't want to do all this work or made a mistake, you can grab the pre-sliced version from the Sample folder. What we've accomplished here is defining which parts of each sprite can stretch and which parts should remain fixed.

### The Line Presenter

Next, we'll modify the Line Presenter to use our custom sprites instead of the default visuals.

1. Select the Dialogue System prefab in the Hierarchy
2. Expand out the `Canvas -> Line View` and select the `Background` gameobject
3. In the `Image` component of the Inspector change the Source Image to be our freshly sliced `Background` sprite
4. In the `Image` component of the Inspector change the Color to be fully opaque white
5. In the `Image` component of the Inspector change the Image Type dropdown to be `Sliced`
6. In the Hierarchy select the Line View game object
7. In the Vertical Layout Group component set the Left and Right padding to be `40`, the Top to be `24`, The bottom to be `115` and set the Spacing to be `20`

Now we need to make the line presenter use our custom font.

1. Select the Text Mesh Pro field inside of `Dialogue System -> Canvas -> Line View -> Character Name`
2. In the Inspector on the Text Mesh Pro component change the Font Asset field to point to the Pixelify-Sans font
3. Set the font size to be `48`
4. Select the Text Mesh Pro field inside of `Dialogue System -> Canvas -> Line View -> Text`
5. In the Inspector on the Text Mesh Pro component change the Font Asset field to point to the Pixelify-Sans font
6. Set the font size to be `50`
7. Expand the Extra Settings section and find the Margins
8. Set the margins to be Left `20`, Top `0`, Right `20`, and Bottom `0`

With that, our line presenter is finished! We can test it to see how it looks in action.

![Our rethemed line presenter](<../../.gitbook/assets/01 (3).png>)

### The Options Presenter

We're halfway there! Now we need to apply similar changes to our options presenter. This has a slight additional step—we'll need to make a prefab for our option items—but otherwise the process is similar to what we did for the line presenter. Let's start by creating the options item prefab, which requires the most work.

1. Right click on the Options Presenter `Dialogue Systemm -> Canvas -> Options View` and add a new `UI -> Text - TextMeshPro` child game object
2. Rename it to be `Option Item`
3. Select the Option Item and in the Inspector find the Text Mesh Pro component
4. Change the Font Asset to point to Pixelify-Sans font
5. Set the Font Size to be `50`
6. Expand out the Extra Settings
7. Set the margins to be Left `30`, and Top, Right and Bottom to all be `0`
8. Add a new Image child game object to the Option Item
9. Rename it to be called Selection Indicator
10. Make it so it is a full height stretch but with a fixed width of `20`
11. Select the Options Item in the Hierarchy
12. Add an Options Item component onto the game object
13. In the Text field drag the Option Item game object in
14. In the Selection Image field drag in the Selection Indicator game object
15. Expand out the Selected section of the inspector
16. Set the Selected sprite to be the `Option-Selected` sprite
17. Drag the Option Item game object out of the Hierarchy into the Assets to make it a prefab
18. Delete the existing Option Item game object, it has served it's purpose

With that done, our final steps are to modify the Options Presenter to use our new Option Item.

1. Select the Options View game object in the Hierarchy
2. In the Inspector find the Options View Prefab field inside the Options Presenter component
3. Replace the existing prefab with our Option Item prefab we made above
4. Select the Background child game object of the option presenter
5. In the Inspector find the Image component
6. Set the Source Image to be our `Background` sprite
7. Set the Color to be fully opaque white
8. Set the Image Type to be `Sliced`
9. Select the Last Line child game object
10. In the Inspector on the Text Mesh Pro component change the Font Asset field to point to the Pixelify-Sans font
11. Change the Font Size to be 48
12. Set the Font to be using Bold
13. Expand the Extra Settings and change the Margins to be Left, Right and Top to be `0`, and set Bottom to be `14`

And with that, our Options Presenter is also rethemed!

![Our restyled options presenter](<../../.gitbook/assets/04 (1).png>)

### Congrats!

With these straightforward changes, we've completely transformed the look of the default dialogue presenters without writing any code. Hopefully, you now feel confident in your ability to customize the visuals of built-in presenters. Take your newly styled dialogue system for a spin and see how it enhances your game's visual identity!
