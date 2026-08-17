# Samla poäng och föremål

## Steg 1: Poängvariabel

~hint Poäng

---

En **poäng** visar hur bra du spelar. Den gör att spelet kan ge dig **feedback** när du gör rätt saker, till exempel när du samlar ett föremål.

hint~

Gå till **Info** och hämta blocket `||info:set score to 0||`. Lägg det i början av koden.

~hint Kort förklaring

---

En **variabel** kan hålla reda på poängen. När du samlar ett föremål ökar du värdet och visar det på skärmen.

hint~

```blocks
scene.setBackgroundImage(img`.`)
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero, 200, 200)
//@highlight
info.setScore(0)
```

## Steg 2: Skapa ett föremål

~hint Föremål

---

Ett **föremål** i ett spel kan vara allt från en nyckel till en frukt eller ett mynt. Här ska det vara något du kan samla in.

hint~

Skapa ett nytt **Sprite-objekt** och ge det typen `Pynt`. Rita ett enkelt föremål.

~hint Kort förklaring

---

När du skapar ett **Sprite-objekt** i en ny typ kan du sedan skriva regler för vad som händer när det kolliderar eller overlappar din spelare.

hint~

```blocks
scene.setBackgroundImage(img`.`)
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero, 200, 200)
info.setScore(0)
//@highlight
let pynt = sprites.create(img`.`, SpriteKind.Pynt)
pynt.setPosition(40, 60)
```

## Steg 3: Kollision och samling

~hint Kollision

---

En **kollision** sker när två objekt rör vid varandra. I spel används detta för att avgöra när spelaren träffar något viktigt.

hint~

Gå till **Sprites** och hämta `||sprites:on overlap||`.

Ställ in blocket så att det reagerar när `Player` överlappar `Pynt`.

I blocket lägger du sedan in:

- `info.changeScoreBy(1)`
- `pynt.destroy()`

~hint Kort förklaring

---

Detta betyder: “När spelaren rör föremålet, ökar poängen med 1 och föremålet försvinner.”

hint~

```blocks
scene.setBackgroundImage(img`.`)
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero, 200, 200)
info.setScore(0)
let pynt = sprites.create(img`.`, SpriteKind.Pynt)
pynt.setPosition(40, 60)
//@highlight
sprites.onOverlap(SpriteKind.Player, SpriteKind.Pynt, function (sprite, otherSprite) {
    info.changeScoreBy(1)
    otherSprite.destroy()
})
```

## Steg 4: Respawn

~hint Respawn

---

När ett föremål tas upp vill du ofta att det ska **dyka upp igen** någon annanstans. Då är det en **respawn**: ett nytt föremål skapas på en ny position.

hint~

Lägg in ett nytt `||sprites:set mySprite to sprite [ ] of kind Pynt||` efter att föremålet förstörts. Ge det en ny slumpmässig position med `randint(0, 160)` och `randint(0, 120)`.

~hint Kort förklaring

---

Nu kan spelaren samla poäng flera gånger. Varje gång ett föremål tas upp kommer ett nytt föremål att dyka upp på en annan plats.

hint~

```blocks
scene.setBackgroundImage(img`.`)
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero, 200, 200)
info.setScore(0)
let pynt = sprites.create(img`.`, SpriteKind.Pynt)
pynt.setPosition(40, 60)
// @highlight
sprites.onOverlap(SpriteKind.Player, SpriteKind.Pynt, function (sprite, otherSprite) {
    info.changeScoreBy(1)
    otherSprite.destroy()
    pynt = sprites.create(img`.`, SpriteKind.Pynt)
    pynt.setPosition(randint(0, 160), randint(0, 120))
})
```

## Steg 5: Utmaning

~hint Utmaning

---

Testa att göra din spelare snabbare, skapa flera föremål eller skapa ett mål som visar “du vann” när poängen når 5.

hint~

Det här är den perfekta början på ett riktigt spel. Du har nu lärt dig:

- hur man håller koll på poäng
- hur man ser när två objekt rör varandra
- hur man gör något när det händer
- hur man respawnar ett föremål

Nästa steg kan vara ett timer-system, ett game over eller en nivå med fiender.
