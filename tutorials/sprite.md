# Skapa din första Sprite

## Steg 1: Variabel, Objekt och Sprite

~hint Variabel

---

En **variabel** är som en låda där spelet sparar information.

hint~

~hint Objekt

---

Ett **objekt** är en mer komplex form av **variabel** som har egna **variabler** i sig. Det kan vara till exempel position eller färg. Ett objekt brukar också ha egna **funktioner** som kan göra saker, till exempel flytta på sig.

hint~

~hint Sprite

---

En **Sprite** är ett speciellt slags **objekt** som fungerar som en spelfigur.

hint~


Klicka på `||sprites: Sprites||` och dra fram `||sprites:set mySprite to sprite [ ] of kind Player||` och lägg det i `||loops:on start||`. 

Klicka på ordet `mySprite`, välj **Rename variable...** och byt namn till något passande, till exempel "hero". 

Klicka på den grå rutan för att rita din hjälte.


~hint Kort förklaring

---

Koden skapar din figur. **Variabeln** som heter `hero` hjälper spelet att hålla koll på exakt vilken **sprite** som är din huvudperson.

hint~

```blocks
//@highlight
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

## Steg 2: Koordinater (X och Y)

~hint Koordinater (X och Y)

---

Skärmen är som ett osynligt rutnät. **X** bestämmer var figuren är i sidled, och **Y** bestämmer var den är i höjdled. Dessa värden kallas **koordinater**.

hint~

Hämta `||sprites:set hero position to x [20] y [20]||` och sätt det under förra blocket. Ändra siffrorna för att flytta figuren.

~hint Kort förklaring

---

Din **Sprite** är ett **objekt**, vilket betyder att den kan minnas sina egna **X- och Y-koordinater**. Om du ändrar X och Y hoppar figuren direkt till den nya platsen.

hint~

```blocks
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
//@highlight
hero.setPosition(20, 20)
```

## Steg 3: Flaggor och Egenskaper 

~hint Boolean

---

En **Boolean** är ett värde som bara kan vara **sant** eller **falskt**. 

I MakeCode känner du igen dessa block på att de har **spetsiga kanter** `< >`.

hint~

~hint Flagga

---

När en **Boolean** (sant/falskt) används som en fast inställning inuti ett objekt kallas den ofta för en **flagga**. 

Den fungerar då som en strömbrytare som slår PÅ eller AV en specifik **egenskap** hos din figur. Till exempel om den ska visa sin fysik (position och hastighet).

hint~

Hämta `||sprites:set hero auto destroy [ON]||` och lägg det sist. Klicka på `auto destroy` och ändra till `show physics`.

~hint Kort förklaring

---

När du aktiverar denna **flagga**, det vill säga ställer den på `ON`, visar spelet information om ditt **Sprite-objekt** direkt på skärmen, till exempel dess nuvarande **koordinater**.

hint~

```blocks
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
//@highlight
hero.setFlag(SpriteFlag.ShowPhysics, true)
```

## Steg 4: Input

~hint Input

---

**Input** betyder inmatning, alltså att du skickar signaler med knapparna för att styra **objekten** i spelet.

hint~

Hämta `||controller:move hero with buttons||` och lägg det sist i koden.

~hint Kort förklaring

---

Detta block talar om för spelet att det specifika **Sprite-objektet** som ligger i **variabeln** `hero` ska uppdatera sina **koordinater** när du ger spelet **input** (när du trycker på pilknapparna).

hint~

```blocks
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
//@highlight
controller.moveSprite(hero)
```

## Steg 5: Hastighet och Parametrar

~hint Hastighet (vx och vy)

---

Hastighet är hur snabbt figuren rör sig åt sidan (vx) eller upp och ner (vy). 

hint~

~hint Parametrar

---

Siffrorna du skriver in i blocken kallas **parametrar**.

hint~

Klicka på plustecknet **(+)** på blocket `||controller:move hero with buttons||`. Ändra siffrorna till **200** för både vx och vy.

~hint Kort förklaring

---

Genom att skriva in högre siffror (**parametrar**) ökar du hastigheten på din **Sprite** när den styrs av din **input**.

hint~

```blocks
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
//@highlight
controller.moveSprite(hero, 200, 200)
```