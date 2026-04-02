# Aktivitet 2

## Steg 1

```blocks
let mySprite = sprites.create(img`
    . . . . . . . .
    . . . 1 1 . . .
    . . 1 1 1 1 . .
    . . 1 1 1 1 . .
    . . . 1 1 . . .
    . . . . . . . .
`, SpriteKind.Player)
```

Steg 2

```blocks
let mySprite = sprites.create(img`
    . . . . . . . .
    . . . 1 1 . . .
    . . 1 1 1 1 . .
    . . 1 1 1 1 . .
    . . . 1 1 . . .
    . . . . . . . .
`, SpriteKind.Player)
controller.moveSprite(mySprite)
```