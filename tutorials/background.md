# Ge din hjälte en miljö

```template
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero, 200, 200)
```

## Steg 1: Bakgrundsbild
Nu svävar din figur i ett svart hål! Låt oss måla hela skärmen. Vill du rita en egen värld? Kanske en skog, en stad eller yttre rymden? 🌌

Gå till **Scene**, hämta `||scene:set background image to [ ]||` och sätt det högst upp i din kod. Klicka på den grå rutan och rita din drömvärld!

```blocks
scene.setBackgroundImage(img`.`)
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero, 200, 200)
```

## Steg 2: Dekorera med sprites
Världen ser lite tom ut. Vi kan ställa ut roliga saker i den, som ett träd eller en sten! 🌳🪨

Hämta ett nytt sprite-block: `||sprites:set pynt to sprite [ ] of kind Player||`. Sätt det längst ner. 
Ett träd är ju varken en spelare eller mat. Klicka på ordet `Player` på blocket, välj **Add a new kind...** och döp den till **Pynt**! Klicka sedan på rutan och rita ditt pynt.

```blocks
scene.setBackgroundImage(img`.`)
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero, 200, 200)
let pynt = sprites.create(img`.`, SpriteKind.Pynt)
```

## Steg 3: Slumpmässig plats 🎲
Nu hamnar ditt pynt mitt på skärmen. Låt oss be datorn lägga det på en hemlig, slumpmässig plats! Eftersom spelskärmen är exakt 160 pixlar bred och 120 pixlar hög, kan vi använda de siffrorna för att täcka hela ytan.

Hämta `||sprites:set pynt position to x [ ] y [ ]||` och sätt det under ditt pynt.
Gå sedan till **Math**, hämta blocket `||math:pick random 0 to 10||` och sätt in i både X och Y. Ändra sista siffran till **160** för X och **120** för Y. Klicka på omstartsknappen i simulatorn några gånger för att se hur pyntet hoppar runt!

```blocks
scene.setBackgroundImage(img`.`)
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero, 200, 200)
let pynt = sprites.create(img`.`, SpriteKind.Pynt)
pynt.setPosition(randint(0, 160), randint(0, 120))
```

## Steg 4: Massor av pynt!
Vill du ha mer än en sak? Vi kan be datorn göra kopior snabbt som blixten med en loop! 🪄

Gå till **Loops**, hämta blocket `||loops:repeat 4 times||`. Dra det blocket så att det hamnar **runt** dina två sista block (både skapandet av pyntet och positionen ska vara inuti). Nu ritar datorn ut 4 stycken på helt olika platser!

```blocks
scene.setBackgroundImage(img`.`)
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero, 200, 200)
for (let index = 0; index < 4; index++) {
    let pynt = sprites.create(img`.`, SpriteKind.Pynt)
    pynt.setPosition(randint(0, 160), randint(0, 120))
}
```

## Färdigt! @showdialog
Snyggt jobbat! Nu har din figur en helt egen värld att springa runt i. ✨