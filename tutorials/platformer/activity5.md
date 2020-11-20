# Enemy AI

```jres
{
    "transparency16": {
        "data": "hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==",
        "mimeType": "image/x-mkcd-f4",
        "tilemapTile": true
    },
    "tile1": {
        "data": "hwQQABAAAADMzMzMzMzMzLy7u7u7u7vLvMvMzMzMvMu8vMzMzMzLy7zMy8zMvMzLvMy8zMzLzMu8zMzLvMzMy7zMzLzLzMzLvMzMvMvMzMu8zMzLvMzMy7zMvMzMy8zLvMzLzMy8zMu8vMzMzMzLy7zLzMzMzLzLvLu7u7u7u8vMzMzMzMzMzA==",
        "mimeType": "image/x-mkcd-f4",
        "tilemapTile": true
    },
    "tile2": {
        "data": "hwQQABAAAAAiIiIiIiIiIkJEREREREQkQiIiIiIiIiRCIiIiIiIiJEIiREQiIiIkQkJERCIkJCRCQiREJCQkJEJCREQiQiIkQkJERCRCIiRCQiREIiQkJEIiREQkJCQkQiIiIiIiIiRCIiIiIiIiJEIiIiIiIiIkQkRERERERCQiIiIiIiIiIg==",
        "mimeType": "image/x-mkcd-f4",
        "tilemapTile": true
    },
    "tile3": {
        "data": "hwQQABAAAAB3d3d3d3d3d1dVVVVVVVV1V3d3d3d3d3VXd3d3d3d3dVdXVVVVVXd1V1dXV3d3d3VXV3VVd3d3dVdXV1d3d3d1V3d1dXV3d3VXd1VXdXd3dVd3dXV1d3d1V3dVVXV3d3VXd3d3d3d3dVd3d3d3d3d1V1VVVVVVVXV3d3d3d3d3dw==",
        "mimeType": "image/x-mkcd-f4",
        "tilemapTile": true
    },
    "tile4": {
        "data": "hwQQABAAAABERERERERERFRVVVVVVVVFVEREREREREVURFRFRERERVRERVRERERFVFRVVUVEREVUVFVVVURFRVRUVVVVVUVFVFRVVVVVRUVUVFVVVURFRVRUVVVFRERFVERFVEREREVURFRFRERERVRERERERERFVFVVVVVVVUVERERERERERA==",
        "mimeType": "image/x-mkcd-f4",
        "tilemapTile": true
    },
    "tile5": {
        "data": "hwQQABAAAACqqqqqqqqqqrq7u7u7u7uruqqqqqqqqqu6qqqqqqqqq7qqqqqqqqqruqqqqqqqqqu6qrurqqqqq7q6u7u7uqururq7u7u6q6u6qrurqqqqq7qqqqqqqqqruqqqqqqqqqu6qqqqqqqqq7qqqqqqqqqruru7u7u7u6uqqqqqqqqqqg==",
        "mimeType": "image/x-mkcd-f4",
        "tilemapTile": true
    },
    "level": {
        "id": "level",
        "mimeType": "application/mkcd-tilemap",
        "data": "MTAxZTAwMGEwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDQwMDAwMDAwMDAwMDQwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAzMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTAxMDEwMDAyMDAwMDAwMDEwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAwMDEwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMjIwMjAwMDAwMjAwMDAwMDAwMDAwMDAwMDAwMDIwMjIyMjIyMjIwMjAwMDAwMjAwMDAyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMg==",
        "tileset": [
            "myTiles.transparency16",
            "myTiles.tile1",
            "myTiles.tile3",
            "myTiles.tile4",
            "myTiles.tile5"
        ]
    },
    "*": {
        "mimeType": "image/x-mkcd-f4",
        "dataEncoding": "base64",
        "namespace": "myTiles"
    }
}
```

```template
scene.onOverlapTile(SpriteKind.Player, myTiles.tile2, function (sprite, location) {
    game.over(false)
})
scene.onOverlapTile(SpriteKind.Player, myTiles.tile4, function (sprite, location) {
    game.over(true)
})
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    thePlayer.vy = -200
})
let newEnemy: Sprite = null
let thePlayer: Sprite = null
scene.setBackgroundColor(11)
thePlayer = sprites.create(img`
    3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3
    3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 3
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3
    3 1 3 3 1 1 1 3 3 3 1 3 3 3 1 3
    3 1 3 3 1 3 3 1 3 1 1 3 3 3 1 3
    3 1 3 3 1 3 3 1 3 3 1 3 3 3 1 3
    3 1 3 3 1 1 1 3 3 3 1 3 3 3 1 3
    3 1 3 3 1 3 3 3 3 3 1 3 3 3 1 3
    3 1 3 3 1 3 3 3 3 1 1 1 3 3 1 3
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3
    3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 3
    3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3
    `, SpriteKind.Player)
thePlayer.ay = 500
controller.moveSprite(thePlayer, 100, 0)
tiles.setTilemap(tilemap`level`)
scene.cameraFollowSprite(thePlayer)
tiles.placeOnRandomTile(thePlayer, myTiles.tile3)
for (let value of tiles.getTilesByType(myTiles.tile5)) {
    newEnemy = sprites.create(img`
        a a a a a a a a a a a a a a a a
        a b b b b b b b b b b b b b b a
        a b a a a a a a a a a a a a b a
        a b a a b b a a a a b b a a b a
        a b a a a a b a a b a a a a b a
        a b a a a a a a a a a a a a b a
        a b a a a b a a a a b a a a b a
        a b a a a b a a a a b a a a b a
        a b a a a a a a a a a a a a b a
        a b a a a a a a a a a a a a b a
        a b a a a b b b b b b a a a b a
        a b a a b a a a a a a b a a b a
        a b a a a a a a a a a a a a b a
        a b a a a a a a a a a a a a b a
        a b b b b b b b b b b b b b b a
        a a a a a a a a a a a a a a a a
        `, SpriteKind.Enemy)
    newEnemy.ay = 500
    tiles.placeOnTile(newEnemy, value)
    newEnemy.setVelocity(-30, 0)
}
```

## Start

In this lesson we'll learn how to make enemies with a simple AI.

Take a look at the code in this program.
It's already spawning enemies from the purple "!" tiles in the game.
When the enemies spawn, they immediately start moving to the left and get stuck on a wall.
We're going to add some logic to help these enemies move around without getting trapped.


## AI Rules

The enemies we create will follow two rules:

1. If the enemy hits a wall, it will turn around
2. If the enemy is walking towards a wall, it will try to jump over it

We can think of these rules as a *condition* and an *action*.
If the condition is met, the action will happen.
We'll need to write some code to check each of the conditions in every game update.

## Looping pt. 1

Drag out an ``||game:on game update||`` block and place it on the workspace.

We want to loop over all of our enemies inside of this event.
For that, we'll be using a ``||loops: for value of list||`` block.
Drag one out and place it inside the ``||game:on game update||``.

```blocks
let list: number[] = [];
game.onUpdate(function () {
    for (let value of list) {
    }
})
```

## Looping pt. 2

On each update, we want our loop to run for every enemy in the game.
To get a list of enemies, we can use the ``||arrays:array of sprite of kind||`` block from the Arrays category.

Drag it out and place it on top of the list variable in the ``||loops: for value of list||`` block.
Change the kind dropdown to Enemy.

```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
    }
})
```

## Wall bouncing pt. 1

Let's add some code for our first rule:

> *If the enemy hits a wall, it will turn around*

First, we need to detect if our enemy is hitting a wall.
We'll use an ``||logic:if then||`` block to run some code only if that condition is met.
Drag out an ``||logic:if then||`` block and place it inside of our loop.

```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (false) {
        }
    }
})
```

## Wall bouncing pt. 2

To check if the enemy is hitting a wall, we can use the ``||scene: sprite is hitting wall left||`` block.
Drag that block into the condition for the ``||logic:if then||``.
For the first argument, drag the "value" from the loop and place it on top of the sprite variable.
For the second, select the direction "left".

Inside the ``||logic:if then||`` place a ``||sprites:set sprite x to||`` block and change "x" to "vx (velocity x)" and the value to 30.
For the sprite argument, drag out another "value" from the loop and place it on top.

```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (value.isHittingTile(CollisionDirection.Left)) {
            value.setVelocity(30, 0)
        }
    }
})
```

## Wall bouncing pt. 3

Now let's handle if the enemy is moving *right*.
Press the "+" button on ``||logic:if then||`` twice to add an "else if" condition.
Now drag out the same blocks as you did for left, but this time select "right" and change the "vx (velocity x)" to be -30.

Take a look at your game! The enemies should be bouncing left and right.

```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (value.isHittingTile(CollisionDirection.Left)) {
            value.setVelocity(30, 0)
        } else if (value.isHittingTile(CollisionDirection.Right)) {
            value.setVelocity(-30, 0)
        }
        else {
        }
    }
})
```

## Jumping pt. 1

Let's take a look at our second rule

> *If the enemy is walking towards a wall, it will try to jump over it*

For this rule, we're first goint to need to make sure our enemy is on the ground.
Press the "+" button on ``||logic:if then||`` to add an "else if" condition.
Place another ``||scene: sprite is hitting wall left||`` block inside the condition and change the variable to "value" and the direction to "bottom".

```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (value.isHittingTile(CollisionDirection.Left)) {
            value.setVelocity(30, 0)
        } else if (value.isHittingTile(CollisionDirection.Right)) {
            value.setVelocity(-30, 0)
        } else if (value.isHittingTile(CollisionDirection.Bottom)) {
        }
        else {
        }
    }
})
```

## Jumping pt. 2

Once again, we need to check both directions that the enemy can be walking.
Drag out another ``||logic:if then||`` and place it inside of the "is hitting wall bottom" check.

```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (value.isHittingTile(CollisionDirection.Left)) {
            value.setVelocity(30, 0)
        } else if (value.isHittingTile(CollisionDirection.Right)) {
            value.setVelocity(-30, 0)
        } else if (value.isHittingTile(CollisionDirection.Bottom)) {
            if (false) {
            }
        }
        else {
        }
    }
})
```

## Jumping pt. 3

To check if the enemy is approaching a wall in a direction, we need to check two things:

1. Is the enemy vx (velocity x) moving it in that direction
2. Is the next tile in that direction a wall

Because we have two things to check, we'll use an ``||logic:and||`` block.
Drag one out and place it in the condition for the ``||logic:if then||``.

```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (value.isHittingTile(CollisionDirection.Left)) {
            value.setVelocity(30, 0)
        } else if (value.isHittingTile(CollisionDirection.Right)) {
            value.setVelocity(-30, 0)
        } else if (value.isHittingTile(CollisionDirection.Bottom)) {
            if (false && false) {
            }
        }
    }
})
```

## Jumping pt. 4

First let's check the vx (velocity x) of the enemy to see if they are moving left.
In MakeCode Arcade, this means that we need to check if the vx of the sprite is negative.
Drag out a ``||logic:0 < 0||`` block and place it in the first part of our ``||logic:and||``.
Drag out a ``||sprites:sprite x||`` block and place it in the left-hand side of the ``||logic:0 < 0||``.
Change the variable to be the "value" from the loop.

```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (value.isHittingTile(CollisionDirection.Left)) {
            value.setVelocity(30, 0)
        } else if (value.isHittingTile(CollisionDirection.Right)) {
            value.setVelocity(-30, 0)
        } else if (value.isHittingTile(CollisionDirection.Bottom)) {
            if (value.vx < 0 && false) {
            }
        }
    }
})
```

## Jumping pt. 5

Now let's check for a wall.
In the second part of the ``||logic:and||`` block, place a ``||scene: tile to left of sprite is||`` block.
Change the variable to be the "value" from the loop and the tile to be the ground/wall tile in our game.

```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (value.isHittingTile(CollisionDirection.Left)) {
            value.setVelocity(30, 0)
        } else if (value.isHittingTile(CollisionDirection.Right)) {
            value.setVelocity(-30, 0)
        } else if (value.isHittingTile(CollisionDirection.Bottom)) {
            if (value.vx < 0 && value.tileKindAt(TileDirection.Left, myTiles.tile1)) {
            }
        }
    }
})
```

## Jumping pt. 6

Inside the ``||logic:if then||`` place a ``||sprites:set sprite x to||`` block and change "x" to "vy (velocity y)" and the value to -150.
For the sprite argument, drag out another "value" from the loop and place it on top.

```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (value.isHittingTile(CollisionDirection.Left)) {
            value.setVelocity(30, 0)
        } else if (value.isHittingTile(CollisionDirection.Right)) {
            value.setVelocity(-30, 0)
        } else if (value.isHittingTile(CollisionDirection.Bottom)) {
            if (value.vx < 0 && value.tileKindAt(TileDirection.Left, myTiles.tile1)) {
                value.vy = -150
            }
        }
    }
})
```


## Jumping pt. 7

Great! Now our enemies will jump when they are heading to the left.
To make this also work for the right, add an "else if" condition to the ``||logic:if then||`` and drag out the same blocks as before.
This time, change "left" to "right" and "<" to ">".

```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (value.isHittingTile(CollisionDirection.Left)) {
            value.setVelocity(30, 0)
        } else if (value.isHittingTile(CollisionDirection.Right)) {
            value.setVelocity(-30, 0)
        } else if (value.isHittingTile(CollisionDirection.Bottom)) {
            if (value.vx < 0 && value.tileKindAt(TileDirection.Left, myTiles.tile1)) {
                value.vy = -150
            } else if (value.vx > 0 && value.tileKindAt(TileDirection.Right, myTiles.tile1)) {
                value.vy = -150
            }
        }
    }
})
```

## Finish

Alright, we've created enemies that know how to get around our world.
Try opening the tilemap editor and making your own level.
