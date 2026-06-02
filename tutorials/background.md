# Ge din hjälte en miljö

## Steg 1: Scen (Scene)

~hint Scen (Scene)

---

**Scenen** är själva bakgrunden i spelet. Den ligger alltid längst bak, helt oberoende av dina rörliga **Sprite-objekt**.

hint~

Gå till **Scene**, hämta `||scene:set background image to [ ]||` och lägg det allra högst upp. Klicka på den grå rutan och rita din bakgrund.

~hint Kort förklaring

---

Nu har du en fast bakgrundsbild som ligger helt stilla medan dina **Sprites** rör sig framför den.

hint~

```blocks
//@highlight
scene.setBackgroundImage(img`.`)
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero, 200, 200)
```

## Steg 2: Klasser och Typer (SpriteKind)

~hint Klasser och Typer (SpriteKind)

---

En **Typ** (Kind) talar om för spelmotorn vilken kategori en specifik **Sprite** tillhör.

hint~

Hämta ett nytt `||sprites:set mySprite to sprite [ ] of kind Player||` och lägg det längst ner. Byt namn på variabeln från "mySprite" till "pynt".

Byt typ genom att klicka på `Player`, välj **Add a new kind...** och döp den till **Pynt**. 

Rita sedan ditt pynt i rutan. 

~hint Kort förklaring

---

När spelet vet att din nya **Sprite** (som sparas i **variabeln** `pynt`) är av **typen** "Pynt", kan du senare bygga regler för vad som händer när detta **objekt** krockar med andra **typer**.

hint~

```blocks
scene.setBackgroundImage(img`.`)
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero, 200, 200)
//@highlight
let pynt = sprites.create(img`.`, SpriteKind.Pynt)
```

## Steg 3: Slumptal

~hint Slumptal

---

Ett **slumptal** är när datorn lottar fram en siffra, istället för att du skriver in en fast **parameter**.

hint~

Hämta `||sprites:set pynt position to x [ ] y [ ]||` och lägg det under pyntet. Gå till **Math**, hämta blocket `||math:pick random 0 to 10||` och lägg ett i X och ett i Y. Ändra högsta siffran till **160** på X och **120** på Y.

~hint Kort förklaring

---

Genom att använda **slumptal** lottar datorn fram nya **X- och Y-koordinater**. Ditt nya **Sprite-objekt** dyker då upp på en ny plats varje gång.

hint~

```blocks
scene.setBackgroundImage(img`.`)
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero, 200, 200)
let pynt = sprites.create(img`.`, SpriteKind.Pynt)
//@highlight
pynt.setPosition(randint(0, 160), randint(0, 120))
```

## Steg 4: Loopar (Iteration)

~hint Loopar (Iteration)

---

En **loop** gör att koden körs om och om igen. Detta gör att du slipper skriva exakt samma block flera gånger.

hint~

Gå till **Loops** och hämta `||loops:repeat 4 times||`. Sätt loopen så att den ramar in dina två sista block.

~hint Kort förklaring

---

Koden upprepas nu fyra gånger på raken. Varje gång skapas ett nytt **Sprite-objekt** som får unika **koordinater** via **slumptal**. Du får direkt fyra pynt på skärmen!

hint~

```blocks
scene.setBackgroundImage(img`.`)
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero, 200, 200)
//@highlight
for (let index = 0; index < 4; index++) {
    let pynt = sprites.create(img`.`, SpriteKind.Pynt)
    pynt.setPosition(randint(0, 160), randint(0, 120))
}
```