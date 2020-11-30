# Adding Fuel

## Introduction @unplugged

Time to refuel! In this tutorial you will add a fuel bar to your spaceship
that goes down as you travel. Make sure to pick up powerups to keep your
ship from breaking down!

We will be using the **Status Bar Extension** in this tutorial. An extension
is an extra set of blocks that can be added to a project. You can browse other
extensions by clicking on ``||images:Extensions||`` under the
**Advanced** category in the editor.

## Step 1
From ``||statusbars:Status Bars||``, drag a ``||variables:set statusbar to||``
``||statusbars:create status bar sprite||`` block into your ``||loops:on start||``.
Set the kind to **Energy**.

```block
let statusbar = statusbars.create(20, 4, StatusBarKind.Energy)
```

## Step 2
Use the ``||statusbars:attach statusbar to mySprite||`` block to attach the
status bar to your ship. You can click the **plus icon** to change the position
of the status bar.

```block
let statusbar = statusbars.create(20, 4, StatusBarKind.Energy)
statusbar.attachToSprite(mySprite, 3, 0)
```

## Step 3
Let's have the fuel go down as time passes. Drag an ``||game:on game update every||``
block into your workspace, and place a ``||statusbars:change statusbar value by||``
block inside. Adjust the time until the speed feels right to you.

```blocks
let statusbar: StatusBarSprite = null
game.onUpdateInterval(200, function () {
    statusbar.value += -1
})
```

## Step 4
Now we'll add some fuel to the game. These could be gas canisters, or energy
crystals, or juicy hamburgers, depending on what kind of vehicle you have.
Drag out an ``||game:on game update every||`` block and change the interval
to **5000**.

```blocks
game.onUpdateInterval(5000, function () {
})
```

## Step 5
Place a ``||variables:set projectile to||`` ``||sprites:projectile from side||``
block in the ``||game:on game update every||``. Rename the variable to
``||variables:fuel||`` and change the ``||sprites:vx||`` value to **0**. Click
on the grey square and draw your refuel item.

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

Place a ``||sprites:set||`` ``||variables:mySprite||`` ``||sprites:kind to||``
block right below the ``||variables:set fuel to||`` ``||sprites:projectile||``
block and change the variable to ``||variables:fuel||``. Select
``||sprites:Add a new kind...||`` from the dropdown and type **Gas**.

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
    fuel.setKind(SpriteKind.Gas)
})
```

## Step 6
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
    fuel.setKind(SpriteKind.Gas)
    fuel.x = randint(0, 160)
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

```templateeffects.starField.startScreenEffect()
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
```

```ghost
statusbar.positionDirection(CollisionDirection.Bottom)
```

```package
pxt-status-bar=github:jwunderl/pxt-status-bar
```