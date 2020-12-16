# Adding Fuel

## Introduction @unplugged

Time to refuel! 

In this tutorial we'll add a fuel bar to your spaceship
that depleats as you travel. 

Make sure to catch the powerups to keep your
ship from breaking down!

![Fuel Up!](/img/space/eat-gas.gif "Is it raining...tacos?")


## Step 1
😵 The starter code is taking up a lot of room! 
Don't worry, the Arcade workspace will expand for you. Just scroll up and
over (or down and over) to keep building.
<hr/>

🔲 Take a peek into the new ``||statusbars:Status Bars||`` category.
You'll find ``||variables:set [statusbar] to create status bar sprite width [20] height [4] kind [Health]||``.
Drag one to the end of the ``||loops:on start||`` container.

🔲 To keep track of how much *gas* is left, set the argument for 
**statusbar** kind to **Energy**.
<hr/>
>> *Tip: The ``||statusbars:Status Bars||`` category is an 
[__extension__](#extendo "a category that provides extended capabilites to MakeCode"). 
To see what else you can do using extensions, 
click ``||statusbars:˅ Advanced||`` and choose ``||extension:Extensions||``*

```block
let statusbar = statusbars.create(20, 4, StatusBarKind.Energy)
```

## Step 2
If we want the status bar to show the details of **mySprite**, we'll need to link the two together.
<hr/>

🔲 Drop ``||statusbars:attach [statusbar] to [mySprite] ⊕||`` 
into the end of the ``||loops:on start||`` container.

🔲 Click ⊕ on the new block to reveal options
 to change the position of the status bar in relation to **mySprite**. 
 Can you figure out how to get the bar to show up *below* your ship?

<br/>

```block
let statusbar = statusbars.create(20, 4, StatusBarKind.Energy)
// @highlight
statusbar.attachToSprite(mySprite, -25, 0)
```

## Step 3
⏰ The longer you're in the air, the more fuel you use ⏰  

Here's how to make the fuel go down as time passes. 
<hr/>
🔲 Drag an ``||game:on game update every [500] ms||`` container into the 
workspace. Adjust the time argument to 300 ms.

🔲 Drop a ``||statusbars:change [statusbar] [value] by [0]||``
block into the **game update** container.

🔲 Change the amount the status bar changes from **0** to **-1**. 
<hr/>

>> *Tip: Remember this step later. If the fuel runs out too fast in 
gameplay, you can come back and adjust these blocks.*


```blocks
let statusbar: StatusBarSprite = null
game.onUpdateInterval(300, function () {
    statusbar.value += -1
})
```

## Step 4
⛽ Time to refuel ⛽

You can drop gas canisters, energy crystals, or juicy hamburgers...whatever 
makes sense for the vessel you have.

The code for dropping fuel is a lot like the code for dropping enemies. 
For a refresher on how things work, find the **myEnemy** blocks in the
workspace and use them as a guide.
<hr/>
🔲 Drag a _new_  ``||game:on game update every [500] ms||`` container 
into the workspace and change the interval to **5 seconds (5000 ms)**.

🔲 Snap a
``||variables:set [projectile2] to||`` ``||sprites:projectile [ ] from side with vx [50] vy [50]||``
block inside the newest **on game update** container.

🔲 Click ``||variables:[projectile2]||`` and rename the sprite ``||variables:[fuel]||``.

🔲 Click on the grey square to bring up the sprite editor so you can
draw a fuel sprite (or choose one from the gallery.) 

🔲 Play with the **vx** and **vy** arguments of the fuel until it's falling
straight down at a decent speed.


```blocks
game.onUpdateInterval(5000, function () {
    let fuel = sprites.createProjectileFromSide(img`
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 . . . . . . . . . . . . . . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . . . . 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 . . 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 . 5 5 5 5 . 5
        5 . 5 5 5 5 . . . . 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . . . . . . . . . . . . . . 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        `, 0, 50)
})
```
## Step 5
Place a ``||sprites:set mySprite x||`` block below the ``||variables:set myEnemy to||``
``||sprites:projectile||`` block. Change the variable to ``||variables:myEnemy||``,
then put a ``||Math:pick random 0 to 10||`` in ``||sprites:set mySprite x||``
and change the second number to `160`.

```blocks
namespace SpriteKind {
    export const Gas = SpriteKind.create()
}

game.onUpdateInterval(5000, function () {
    let fuel = sprites.createProjectileFromSide(img`
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 . . . . . . . . . . . . . . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . . . . 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 . . 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 . 5 5 5 5 . 5
        5 . 5 5 5 5 . . . . 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . . . . . . . . . . . . . . 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        `, 0, 50)
        // @highlight
    fuel.x = randint(0, 160)   
})
```

## Step 6

Now we need to put our fuel sprite into the _gas_ class.
<hr/>
🔲 Connect a ``||variables:set [mySprite] kind to [Player]||`` block at the end
of the newest **on game update** container.

🔲 Change ``||variables:mySprite||`` to ``||variables:fuel||``. 

🔲 Click ``||sprites:Player||`` to get the menu, then choose
``||sprites:Add a new kind...||`` and create the type **Gas**.

```blocks
namespace SpriteKind {
    export const Gas = SpriteKind.create()
}

game.onUpdateInterval(5000, function () {
    let fuel = sprites.createProjectileFromSide(img`
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 . . . . . . . . . . . . . . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . . . . 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 . . 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 . 5 5 5 5 . 5
        5 . 5 5 5 5 . . . . 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . . . . . . . . . . . . . . 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        `, 0, 50)
    fuel.x = randint(0, 160) 
    // @highlight  
    fuel.setKind(SpriteKind.Gas)
})
```


## Step 7
Drag a ``||sprites:on overlaps||`` block into the workspace. Change the second
sprite kind to ``||sprites:Gas||``.

```blocks
namespace SpriteKind {
    export const Gas = SpriteKind.create()
}

sprites.onOverlap(SpriteKind.Player, SpriteKind.Gas, function (sprite, otherSprite) {
})
```

## Step 8
Now use the ``||statusbars:set statusbar value||`` block to set your status bar
to **100**. Make sure you also ``||sprites:destroy||`` the ``||variables:otherSprite||``.

```blocks
namespace SpriteKind {
    export const Gas = SpriteKind.create()
}

let statusbar: StatusBarSprite = null
sprites.onOverlap(SpriteKind.Player, SpriteKind.Gas, function (sprite, otherSprite) {
    statusbar.value = 100
    otherSprite.destroy()
})
```

## Step 9
If you run out of fuel, you'll be marooned! Take an ``||statusbars:on status bar kind Health zero||``
block and change the kind to **Energy**. Drag a ``||game:game over||`` block
into it. Test out your game, and try to stay fueled up!

```blocks
statusbars.onZero(StatusBarKind.Energy, function (status) {
    game.over(false)
})
```

```template

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    let projectile = sprites.createProjectileFromSprite(img`
3 3 3 3 3 3 3 3
3 . . . . . . 3
3 . 3 3 3 3 . 3
3 . 3 . . 3 . 3
3 . 3 . . 3 . 3
3 . 3 3 3 3 . 3
3 . . . . . . 3
3 3 3 3 3 3 3 3
    `, mySprite, 0, -70)
    projectile.startEffect(effects.ashes)
})
sprites.onOverlap(SpriteKind.Projectile, SpriteKind.Enemy, function (sprite, otherSprite) {
    sprite.destroy(effects.bubbles, 500)
    otherSprite.destroy(effects.smiles, 500)
})
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    info.changeLifeBy(0)
    otherSprite.destroy(effects.disintegrate, 500)
})
let myEnemy: Sprite = null
effects.starField.startScreenEffect()
let mySprite = sprites.create(img`
    . . . . . . . 9 9 . . . . . . .
    . . . . . . 9 . . 9 . . . . . .
    . . . . . . 9 . . 9 . . . . . .
    . . . . . 9 . 9 9 . 9 . . . . .
    . . . . . 9 . 9 9 . 9 . . . . .
    . . . . 9 . 9 9 9 9 . 9 . . . .
    . . . . 9 . 9 9 9 9 . 9 . . . .
    . . . 9 . 9 9 9 9 9 9 . 9 . . .
    . . . 9 . 9 . . . . 9 . 9 . . .
    . . 9 . 9 9 . 9 9 . 9 9 . 9 . .
    . . 9 . 9 9 . . . . 9 9 . 9 . .
    . 9 . 9 9 9 . 9 9 9 9 9 9 . 9 .
    . 9 . 9 9 9 . 9 9 9 9 9 9 . 9 .
    9 . 9 9 9 9 9 9 9 9 9 9 9 9 . 9
    9 . . . . . . . . . . . . . . 9
    9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9
`, SpriteKind.Player)
controller.moveSprite(mySprite)
mySprite.setFlag(SpriteFlag.StayInScreen, true)
game.onUpdateInterval(500, function () {
    myEnemy = sprites.createProjectileFromSide(img`
        2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2
        2 . . . . . . . . . . . . . . 2
        2 . 2 2 2 2 2 2 2 2 2 2 2 2 . 2
        . 2 . 2 2 2 . . . . 2 2 2 . 2 .
        . 2 . 2 2 2 . 2 2 2 2 2 2 . 2 .
        . . 2 . 2 2 . . . 2 2 2 . 2 . .
        . . 2 . 2 2 . 2 2 2 2 2 . 2 . .
        . . . 2 . 2 . . . . 2 . 2 . . .
        . . . 2 . 2 2 2 2 2 2 . 2 . . .
        . . . . 2 . 2 2 2 2 . 2 . . . .
        . . . . 2 . 2 2 2 2 . 2 . . . .
        . . . . . 2 . 2 2 . 2 . . . . .
        . . . . . 2 . 2 2 . 2 . . . . .
        . . . . . . 2 . . 2 . . . . . .
        . . . . . . 2 . . 2 . . . . . .
        . . . . . . . 2 2 . . . . . . . 
        `, 0, 50)
    myEnemy.x = randint(5, 155)
    myEnemy.setKind(SpriteKind.Enemy)
})

```

```ghost
statusbar.positionDirection(CollisionDirection.Bottom)
```

```package
pxt-status-bar=github:jwunderl/pxt-status-bar
```