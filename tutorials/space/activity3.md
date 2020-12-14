# Adding Danger

## Introduction @unplugged

Intergalactic travel is dangerous!

Let's add some enemies for your ship to avoid.  
These could be asteroids, radioactive debris, or angry space sharks!

![Releasing projectiles](/img/space/projectiles.gif "Here, enemy ship. Would you like to borrow an asteroid?")


## Step 1

Feel like making enemies rain from the sky?

Let's add some code that will drop an enemy toward the ship every second or so.
<hr/> 
🔲 Add an ``||game:on game update every [500] ms||`` container to the workspace  
🔲 Change the last argument to **1000** [__*ms*__](#millis "milliseconds...aka 1/1000 of a second") 
(or pick **1 second** from the dropdown)    
<br/>

```blocks
game.onUpdateInterval(1000, function () {
})
```

## Step 2

🔲 Find the
``||variables:set [projectile2] to||`` ``||sprites:projectile [ ] from side with vx [50] vy [50]||`` block near the bottom of the ``||sprites:Sprites||`` category
and drag it into the ``||game:on game update every [1000] ms||`` container.  
🔲 Click on the ``||variables:[projectile2]||`` argument inside the new block and 
select "Rename variable..."  
🔲 Change the variable name to ``||variables:myEnemy||`` so we know these are the baddies.  

```blocks
let myEnemy: Sprite = null
game.onUpdateInterval(1000, function () {
    // @highlight
    myEnemy = sprites.createProjectileFromSide(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, 50, 50)
})
```

## Step 2.5

🔲 Click the grey square inside the new block to design your enemy (or choose one from the gallery).  
🔲 Play with the **vx** and **vy** values until 
your new sprites are falling straight down the side of the screen. 


```blocks
let myEnemy: Sprite = null
game.onUpdateInterval(1000, function () {
    // @highlight
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
})
```

## Step 3

Place a ``||sprites:set||`` ``||variables:mySprite||`` ``||sprites:kind to||``
block right below the ``||variables:set myEnemy to||`` ``||sprites:projectile||``
block. Change the variable to ``||variables:myEnemy||`` in the dropdown list and
select ``||sprites:Enemy||`` for the kind.

```blocks
let myEnemy: Sprite = null
game.onUpdateInterval(1000, function () {
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
    // @highlight
    myEnemy.setKind(SpriteKind.Enemy)
})
```
## Step 4

Place a ``||sprites:set mySprite x||`` block below the ``||variables:set myEnemy to||`` ``||sprites:projectile||`` block. Change
the variable to ``||variables:myEnemy||`` in the dropdown list.


```blocks
let myEnemy: Sprite = null
game.onUpdateInterval(1000, function () {
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
    myEnemy.setKind(SpriteKind.Enemy)
    // @highlight
    myEnemy.x = 0
})
```

## Step 5

Place a ``||Math:pick random 0 to 10||`` in the ``||sprites:set mySprite x||``
block and change the second number to `160` (the width of the screen).

```blocks
let myEnemy: Sprite = null
game.onUpdateInterval(1000, function () {
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
    myEnemy.setKind(SpriteKind.Enemy)
    // @highlight
    myEnemy.x = randint(0, 160)
})
```

## Step 6

Drag a ``||sprites:on overlaps||`` block into the workspace. Change the second
sprite kind to ``||sprites:Enemy||``.

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {

})
```

## Step 7

Inside the ``||sprites:on overlaps||`` block, place a ``||sprites:destroy sprite||`` block. Drag the
``||variables:otherSprite||`` variable from the ``||sprites:on overlaps||`` block and place it inside
the  ``||sprites:destroy sprite||``.

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    otherSprite.destroy()
})
```

## Step 8

Now go into ``||info:Info||`` and drag a ``||info:change life by||`` block
into ``||sprites:on overlaps||``. Now practice dodging the enemies! If you have
extra time, try experimenting with the ``||scene:camera shake||`` block.

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    otherSprite.destroy()
    info.changeLifeBy(-1)
})
```

## Step 9

Finally, drag another ``||sprites:on overlaps||`` block into the workspace and
change the first sprite kind to ``||sprites:Enemy||`` and the second to
``||sprites:Projectile||``. Drag out two ``||sprites:destroy sprite||`` blocks--we
want to destroy the enemy and your projectile when you hit!

```blocks
sprites.onOverlap(SpriteKind.Enemy, SpriteKind.Projectile, function (sprite, otherSprite) {
    otherSprite.destroy();
    sprite.destroy();
})
```

```template
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
    projectile.startEffect(effects.fire);
})
```

```ghost
scene.cameraShake(4, 500)
```