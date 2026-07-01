# Godot Engine Note | Godot v4.6.3 | 2D GAME
# The current version is after 51 mins of the 1h 41mins vidoe 5330
## REFERENCE
- [GET_START](#get-start)
- [BASICS FEATURES](#basics-features)
- [SCENE](#scene)
- [CREDITS](#credits)


## Intro
>*Top* of the editor screen is the **scene tab**. You might **add a new scene to start** every new a player sprite or background for the game. You do need to **put everything together** in a scene for the game **to work** as expected.(Put everything under the Main scene on the Left panel)

>*Left Panel* gives you **details about of the current scene tab**. The plus sign **creates new Node** and Child Node for your scene, essentially, these Nodes and Child Nodes would build up your game.

## GET START

Download Link: <https://godotengine.org/>

1. Launch Application.
2. `+ Create` to create project.
3. Input Project Name and Project Path.
4. Select `Renderer`.
5. Select `version Control Metadata`.
6. `Create&Edit` to finish setup.


## BASICS FEATURES
- Left Panel : The current working scene and node(s).
- Right Panel : The properties of the selected object/node(s).
- Middle Panel : Scene/Script showcase.
- Zoom in : Top Left Plus Sign on the Scene Screen OR `Mouse Scrolling Forward`.
- Zoom out : Top Left Minus Sign on the Scene Screen OR `Mouse Scrolling Backward`.
- Grid Map : Top of the Scene Screen `Use Grid Snap` OR `Shift + G`.
- Duplicate Objects : Select the object, then use `Ctrl + D` OR `right click` to duplicate.

## SCENE
A Gameplay Scene Might Have:
- [2D Scene](#2d-scene)
    - Button Node
    - Script
    - Label

### 2D Scene
- Left Panel -> under Scene tab -> select `2D Scene` node.
> You might double-click OR right click on the created node to rename it.
- Do `Ctrl + S` OR `right click` the current tab on the Top Panel **to save** the scene.
> Use the top right `Run Project` button OR `F5` to run the scene. 


### 2D Scene/Button Node
Creation Method(s):
- Add child node `Ctrl + A` -> Search bar input `Button` -> Select and Create Button.

\
Properties Usage(s):
- Add text : Select a Button -> on Right Panel, input text under `Text` Title.
- Add a tooltip : Select a Button -> Right Panel, under `Tooltip` subtree -> Input text.
- Add a signal : Select a Button -> Right Panel, under `Signals` tab -> Select a signal.
> You must have a script to add signals.


### Script
Creation Method:
- Select a scene/node -> Top Right of the Left Panel -> click `Attach Node Script`.

Usage(s):
> You might only use those function composition(s) within a signal.
- Quit the application : `get_tree().quit()`.
- Toggle the Scene(s) : `get_tree().change_scene_to_file("[a_specific_scene_path]")`.


### 2D Scene/Label
Creation Method:
- Select a scene -> Add a new node `Ctrl + A` -> Search `label` -> Create it.

Usage(s):
- Add text : Select a label -> on Right Panel, at `Inspector` Tab, input text under `Text` Title.






















## Player
- A Player Sprite Might Have:
    - CharacterBody2D
        - CollisionShape2D
        - AnimatedSprite2D
        - Camera2D
        - AnimationPlayer
        - AnimationTree

### CharacterBody2D/Camera2D
- Right panel, Limit allows user to adjust the area a player's camera can access/see. \
Example: `Left: 0px, Top:0px -> Plyer can't move over to the -1px area.`
### CharacterBody2D/AnimatedSprite2D
- The **default option** for `Sprite Frames` on the Right Panel is blank. Select `SpriteFrames` to get start.
- You MUST click on the `SpriteFrames` to enable SpriteFrames on the Bottom page.
- In SpriteFrames, you can click on `Add Animation` OR `Ctrl + N` to create new animation.
- You might add Sprite Frames to show your Character and its Animation:
    - Method 1: 
        1. Assign your Frames by clicking on the `Add Frames from Sprites Sheet` icon near the `Folder Icon` and `Animation Frames:` Title.
        2. Select the `Path` of the Sprite Sheet Image File to Open the png file.
        3. Once the `Select Frames` tab is open, on your right-hand side, adjust the number for `Horizontal` and `Vertical`, in other word, how many sprite frame are there in a row(horizontal) and in a column(vertical).
        4. Select the `Sprite Frames` you need for your `Animation`.
        5. `Add Frames(s)`
    - Method 2:



## Credits
- Godot Game Development – Crash Course for Beginners created by @CodingQuests on youtube freeCodeCamp.org Channel, Date(year/month/day) - 2023/4/18, [URL](https://www.youtube.com/watch?v=S8lMTwSRoRg).

