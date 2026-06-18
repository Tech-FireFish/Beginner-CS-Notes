# Godot Engine Note Godot v4.6.3
# The current version is after 51 mins of the 1h 41mins vidoe
## REFERENCE
- [Credits](#credits)


## Intro
>*Top* of the editor screen is the **scene tab**. You might **add a new scene to start** every new a player sprite or background for the game. You do need to **put everything together** in a scene for the game **to work** as expected.(Put everything under the Main scene on the Left panel)

>*Left Panel* gives you details about of the current scene tab. The plus sign creates new Node and Child Node for your scene, essentially, these Nodes and Child Nodes would build up your game.

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



## Credits
- Godot Game Development – Crash Course for Beginners created by @CodingQuests on youtube freeCodeCamp.org Channel, Date(year/month/day) - 2023/4/18, [URL](https://www.youtube.com/watch?v=S8lMTwSRoRg).

