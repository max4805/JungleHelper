# Jungle Helper

This repository contains the helper and assets for the _Celeste: Into the Jungle_ mod. Both custom entities / triggers and assets can be used in other maps (with credit) by having this helper as a dependency.

## Custom Entities

- **Attach Trigger Controller**: a controller allowing to attach any trigger to any entity. Place the "T" on the trigger, and the "E" on the entity. If you need filters (because entities or triggers overlap), you can use the controller's properties.
- **Bouncy Shroom**: a mushroom that bounces Madeline. Comes in up, up-left and up-right variants.
- **Breakable Pot**: a pot you can throw on the ground or on a wall to get either a key to open doors, or... a rupee that does nothing.
- **Cassette with Custom Preview Music**: works like a cassette, except you can pick which music event is played when you collect the cassette (if you have custom B-side music), or pick which of the vanilla B-side songs to use. Keep in mind that custom preview events have to be structured like the vanilla one.
- **Cheat Code Controller**: allows the player to enter the vanilla cheat code (Left, Right, Journal, Grab, Up, Up, Down, Left, Grab, Confirm) to enable Cheat Mode and be kicked back to the overworld, like in vanilla Prologue.
- **Cockatiel**: a decorative entity working much like vanilla flutter birds.
- **Climbable One-Way Platform**: a platform you can grab on one side, but that you can also go through if you don't press Grab (contrary to sideways jumpthrus). This is useful to make ropes for example.
- **Cobweb**: Madeline gets stuck in those if she hits them, and can only get out by dashing. Cobwebs are one-use: once Madeline dashed out, the cobweb disappears and does not respawn.
- **Delayed Auto-Falling Block**: a falling block that falls automatically after a set delay. Also has customizable shake time before falling.
- **Dragonfly**: a decorative entity with recolorable wings and randomized animation offset.
- **Falling Killbox**: a killbox... except falling. Useful to prevent the player from going down too fast in a falling section.
- **Firefly**: a flying dot that goes around and follows the player when touched, much like moon creatures.
- **Grabless Golden Berry**: like the vanilla dashless golden berry, except it flies away when the player grabs on a wall.
- **Gecko**: goes up and down on a set path. It can be made to kill the player, or to be purely decorative. It can also be used to show a tutorial similar to the Custom Tutorial Bird (with a _Gecko Tutorial Trigger_ that allows showing or hiding the tutorial bubble).
- **Green Crystal**: much like a Theo crystal, except it cannot be held. It can only be moved around by moving/removing the platform it is standing on.
- **Green Crystal Gate**: a temple gate that only opens when a Green Crystal is nearby.
- **Hawk**: when Madeline touches it, it will carry her to the right until she jumps or dashes out. It has customizable speed.
- **Lantern**: a light the player can grab and keep without having to hold Grab. To drop it, the player can press Down + Grab. She will also lose the lantern when she touches water. When Madeline has the lantern, she cannot dash, but the lantern has effects on a few entities:
  - **Mossy Wall**: moss that sticks to a wall, preventing Madeline from grabbing it, like ice walls. When a lantern gets close, the moss fades away and allows Madeline to climb.
  - **Snake**: an enemy that starts chasing Madeline if she gets too close. When a lantern gets close to its spawn point, the snake gets scared and rushes away to a hiding spot, which is its node.
  - **Spiny Plant**: a vertical plant that kills on touch. When a lantern gets close, the plant retracts, allowing Madeline to pass through without getting hurt.
- **Noded Crumble Platform**: a crumble platform that will move between different positions before respawning.
- **Predator Plant**: a plant attacking Madeline when she gets close. Madeline can be killed by the plant, but can also jump on it to bounce.
- **Rolling Rock**: a boulder that starts rolling when Madeline walks to the right of it, and goes right. It breaks dash blocks along the way, and shatters if it hits a wall.
- **Slide Block**: a Kevin-looking block that moves in the direction Madeline is dashing. Once the block moved once, it needs to be refilled to move again. Comes in restrained (green) and restraintless (red) versions: restrained blocks stop after they moved by their own width/height; restraintless blocks move until they hit a wall or the edge of the screen.
- **Slide Block Refill**: a refill that can be collected by the player to refill all slide blocks in the room, so that they can be moved again.
- **Spider Boss**: a spider that falls down from the top of the screen, killing Madeline if she hits it. The spider color determines its difficulty: Blue, Purple and Red in this order, with Red being the one falling the most often, and tracking the player at the fastest speed.
- **Swing Cassette Block**: cassette blocks that play their music in a 66-34-66-34... pattern instead of 50-50-50-50...
- **Torch**: a torch that sets a session flag when Madeline lights it by touching it.
- **Treasure Chest**: a chest that opens with a key, and spawns a crystal heart when open.
- **Zip Moving Platform**: a moving platform behaving much like a zip mover.

## Custom Triggers

- **Drop Lantern Trigger**: a trigger that forces Madeline to drop her lantern. The lantern can either just fall on the ground, or be destroyed (in that case, it fades out on the ground and goes back to its spawn point).
- **Gecko Tutorial Trigger**: much like the Custom Bird Tutorial Trigger from Everest, it allows to show/hide the tutorial bubble of a gecko (see previous section).
- **UI Image Trigger**: a high-res image will be shown on-screen when Madeline enters the trigger, and will fade out when she leaves it.
- **UI Text Trigger**: text will be shown on-screen when Madeline enters the trigger, and will fade out when she leaves it.

## Reskinned Entities included in the pack

Those are reskinned entities that are placeable in Ahorn.

- **Crumble Block**: Dark, Mossy, Thin, Mosaic
- **Jump Through**: Invisible, Plank
- **Moving Platform**: Escape, Jungle, Night
- **Sinking Platform**: Escape, Jungle, Night
- **Spikes**: Ruins, Wood, Wood Outline
- **Switch Gate**: Stone, Wood

Mosaic Crumble Blocks and Invisible Jump Throughs are custom entities, the other ones are reskins of vanilla entities.

## Custom Decal Registry Attributes

- `<jungleHelper_rainbow>`: gives a rainbow tint to the decal, like rainbow spinners. Also works with rainbow spinner color controllers from max480's Helping Hand.

## Wipes included in the pack

The following wipes are included with the helper, and can be used if you also have [max480's Helping Hand](https://github.com/max4805/MaxHelpingHand):
- **Arrow** with plant-like edges around it
- **Dots** that grow to cover the screen
- **Rocks** that fall off from the top of the screen
- **Spinners** at the edge of a wipe that goes from left to right
- **Vines** that grow to cover the screen

## The Lantern and Skin Mods

Since the Lantern works by changing the player sprites to ones that have Maddy carry the lantern, it is incompatible with skin mods unless those provide sprites for it.

If you have a skin mod installed and enter a map with a lantern, the skin will be disabled and a postcard will be displayed:
> You have a skin mod installed which is not compatible with this campaign.
> It will be re-enabled once you play something else.

If, for consistency's sake, you want to enforce that skin change in your whole campaign, you can place an **Enforce Skin Controller** in maps that don't have a lantern to force the skin change.

**If you are a skin maker** and your skin works by overriding vanilla sprites, you can prevent that from happening by making sprites of your character with the lantern:
- copy textures inside `Graphics/Atlases/Gameplay/JungleHelper/Lantern` and edit them (you don't need the `LanternEntity` folder or `Overlay.png`)
- add Jungle Helper as an optional dependency, to be sure your mod reskins Jungle Helper and not the opposite:
```yaml
- Name: MySkin
  Version: 1.0.0
  OptionalDependencies:
    - Name: JungleHelper
      Version: 1.0.0
```

- if you want to add more animations than what Jungle Helper provides, you can do so by adding frames that match vanilla names in `Graphics/Atlases/Gameplay/JungleHelper/Lantern` and `Graphics/Atlases/Gameplay/JungleHelper/Lantern/Badeline`.
- if you want to change frame counts, animation speeds or anything that involves Sprites.xml editing, copy-paste `junglehelper_madeline_lantern_no_override` or `junglehelper_badeline_lantern_no_override` into your skin's Graphics/Sprites.xml, then tweak it as needed. _For Badeline, you need to copy-paste `junglehelper_player_badeline_copy_vanilla` as well, to ensure the game doesn't crash without Jungle Helper installed._