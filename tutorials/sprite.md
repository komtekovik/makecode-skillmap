# Skapa din första Sprite

## Steg 1: Skapa din hjälte
En **Sprite** är en levande del av spelet, till exempel din spelkaraktär! 👾 

Dra ut `||sprites:set mySprite to sprite [ ] of kind Player||` och lägg den i `||loops:on start||`. Eftersom vår figur ska vara en hjälte vill vi döpa den till det! Klicka på ordet `mySprite` på blocket, välj **Rename variable...** och skriv in **hero**. Klicka sedan på den grå rutan för att rita din figur.

```blocks
let hero = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . 5 5 . . . . . . . 
    . . . . . . 5 5 5 5 . . . . . . 
    . . . . . 5 5 5 5 5 5 . . . . . 
    . . . . . 5 d 5 5 d 5 . . . . . 
    . . . . . 5 5 5 5 5 5 . . . . . 
    . . . . . 5 2 5 5 2 5 . . . . . 
    . . . . . . 5 2 2 5 . . . . . . 
    . . . . . . . 5 5 . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
`, SpriteKind.Player)
```

## Steg 2: Placera den (Koordinater)
Skärmen är som en skattkarta med ett osynligt rutnät. **X** styr hur långt åt sidan figuren är, och **Y** styr upp och ner. De här siffrorna kallas för **koordinater**! 🗺️

Hämta `||sprites:set hero position to x [20] y [20]||` och sätt den under din förra kod. Prova att ändra siffrorna och se vart din figur tar vägen.

```blocks
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(20, 20)
```

## Steg 3: Se siffrorna!
Det finns ett sätt att se spritens koordinater direkt på skärmen. Då ser man precis var **X** och **Y** är! 🔍

Hämta blocket `||sprites:set hero auto destroy [ON]||` och sätt det sist. Klicka på den sista vita rutan och välj **show physics**. Nu dyker det upp siffror på din figur som visar exakt var den är!

```blocks
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
```

## Steg 4: Lär den gå
Nu när vi ser koordinaterna kan vi prova att flytta på figuren.
Hämta blocket `||controller:move hero with buttons||` och lägg det sist i din kod.

Prova att styra med pilarna. Ser du hur siffrorna (koordinaterna) ändras när figuren rör på sig? 

```blocks
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero)
```

## Steg 5: Öka hastigheten 🚀
När du rör på figuren dyker det upp nya siffror under den: **vx** och **vy**. Det är farten! 

Vill du åka supersnabbt? Klicka på det lilla plustecknet **(+)** på ditt röda block `||controller:move hero with buttons||` och ändra siffrorna till till exempel **200**. Prova att köra nu!

```blocks
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero, 200, 200)
```

## Färdigt! @showdialog
Helt fantastiskt jobbat! Du vet nu vad en **Sprite** är, hur **koordinater** fungerar och hur man ändrar **farten** (vx och vy). 🏆