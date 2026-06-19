# Godot Engine Note Godot v4.6.3 FOR 2D GAME
# The current version is after 51 mins of the 1h 41mins vidoe 5330
## REFERENCE
- [GET_START](#get-start)
- [CREDITS](#credits)


## Intro
>*Top* of the editor screen is the **scene tab**. You might **add a new scene to start** every new a player sprite or background for the game. You do need to **put everything together** in a scene for the game **to work** as expected.(Put everything under the Main scene on the Left panel)

>*Left Panel* gives you details about of the current scene tab. The plus sign creates new Node and Child Node for your scene, essentially, these Nodes and Child Nodes would build up your game.

## GET START

Download Link: <https://godotengine.org/>

1. Launch Application.
2. `+ Create` to create project.
3. Input Project Name and Project Path.
4. Select `Renderer`.
5. Select `version Control Metadata`.
6. `Create&Edit` to finish setup.

## Basic Features

















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

