# Ge din hjälte en miljö

```template
let mySprite: Sprite = null
mySprite = sprites.create(img`.`, SpriteKind.Player)
mySprite.setPosition(80, 60)
mySprite.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(mySprite, 200, 200)
```

## Steg 1: Bakgrundsfärg @showdialog
Nu svävar din figur i ett svart hål! Låt oss måla hela skärmen. 🎨

Gå till kategorin **Scene**, hämta blocket `||scene:set background color to [ ]||` och sätt det högst upp i din kod. Klicka på den lilla rutan i blocket och välj en fin färg!

```blocks
scene.setBackgroundColor(7)
let mySprite: Sprite = null
mySprite = sprites.create(img`.`, SpriteKind.Player)
mySprite.setPosition(80, 60)
mySprite.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(mySprite, 200, 200)
```

## Steg 2: Bakgrundsbild
Vill du hellre rita en egen värld? Kanske en skog, en stad eller yttre rymden? 🌌

Ta bort färg-blocket du nyss lade till. Gå till **Scene** igen och hämta istället `||scene:set background image to [ ]||`. Klicka på den grå rutan och rita din drömvärld!

```blocks
scene.setBackgroundImage(img`.`)
let mySprite: Sprite = null
mySprite = sprites.create(img`.`, SpriteKind.Player)
mySprite.setPosition(80, 60)
mySprite.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(mySprite, 200, 200)
```

## Steg 3: Dekorera med sprites
Världen ser lite tom ut. Vi kan ställa ut roliga saker i den, som ett träd eller en sten! 🌳🪨

Hämta ett nytt sprite-block: `||sprites:set mySprite2 to sprite [ ] of kind Player||`. Sätt det längst ner. 
Ett träd är ju varken en spelare eller mat. Klicka på ordet `Player` på blocket, välj **Add a new kind...** och döp den till **Pynt**! Klicka sedan på rutan och rita ditt pynt.

```blocks
scene.setBackgroundImage(img`.`)
let mySprite: Sprite = null
mySprite = sprites.create(img`.`, SpriteKind.Player)
mySprite.setPosition(80, 60)
mySprite.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(mySprite, 200, 200)
let mySprite2 = sprites.create(img`.`, SpriteKind.Pynt)
```

## Färdigt! @showdialog
Snyggt jobbat! Nu har din figur en helt egen värld att springa runt i, full med färg och roliga saker. ✨