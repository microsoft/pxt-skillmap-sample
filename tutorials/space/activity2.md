# Projectiles

## Introduction @unplugged

![Releasing projectiles](/img/space/projectiles.gif "Here, enemy ship. Would you like to borrow an asteroid?" )

Are you ready to customize your ship? 

In this tutorial, you'll learm to fire a projectile when the **A** button
is pressed and add your own special effects.

## Customize sprites

The workspace is pre-loaded with code for a flying ship.

It's up to you to customize the [__*sprite*__](#sprote "2-D image that moves on the screen") and make it your own. You could design a new 
kind of vehicle OR turn it into an alien creature floating through space! 👽

<hr/>

>>*Tip: Remember, to edit a sprite, click inside the grey square where your current sprite is displayed.

![Edit the sprite](/img/space/edit-sprite.png "Click within the square. I dare you!")

## Add a button event

🔲 Drag an ``||controller:on [A] button pressed ||`` container into the workspace, 

🔲 Snap a <br/>
``||variables:set [projectile] to||`` ``||sprites:projectile [ ] from [mySprite] with vx [50] vy [50]||`` 
block inside of it.

🔲 Click on the grey box inside of the new projectile block to draw your 
flying object (or select one from the gallery.)
<hr/>

>>*Tip: Run your code in the simulator and launch a few projectiles 
by pressing the ![The A Button](/img/space/a-button.png "Let's get fired up!") button.  What happens?


```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
let projectile = sprites.createProjectileFromSprite(img`.`, mySprite, 50, 50)
})
```

## Retrospect @unplugged

You probably noticed that your projectiles are firing toward the bottom 
right corner. This is *not helpful* when your enemies are coming from above! Let's take 
a second to figure out what's happening.
<hr/>
The ``||variables:set projectile to||`` block comes preloaded with 
an [__*argument*__](#argue "extra chunk of information that the block needs") 
that sets both the [__*vx*__](#whatVX "horizontal velocity") 
and [__*vy*__](#whatVY "vertical velocity") 
values to 50.

```block
let mySprite: Sprite = null
let projectile = sprites.createProjectileFromSprite(img`.`, mySprite, 50, 50)
```

## Learn Velocity @unplugged

To change the direction of your projectiles,  
you need to change the 
[__*velocity*__](#veloc "speed in a given direction") of the object either:  
- horizontally (in the [__*x*__](#whatX "position from left to right") space) by changing the __vx__  
- vertically (in the [__*y*__](#whatY "position from top to bottom") space) by changing the __vy__  
- or both




## Create a projectile

```blocks
let mySprite: Sprite = null
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    // @highlight
    let projectile = sprites.createProjectileFromSprite(img`.`, mySprite, 0, -70)
})
```


## Draw your projectile

Click on the grey square to open the image editor and draw your projectile.
Try shooting the projectile in the simulator using your keyboard or click
the **A** button.

```blocks
let mySprite: Sprite = null
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    // @highlight
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
})
```

## Custom effects

Time for some special effects! From ``||sprites:Sprites||``, drag the
``||sprites:mySprite start effects||`` block **after**
``||variables:projectile from mySprite||``. Make sure you change the variable
from ``||variables:mySprite||`` to ``||variables:projectile||``, then click on
the dropdown and try out some different effects! You can also use this block
to set an effect on your spaceship.

```blocks
let mySprite: Sprite = null
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
    // @highlight
    projectile.startEffect(effects.fire);
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
```