# Skapa din första Sprite

## Steg 1: Variabel, Objekt och Sprite
**Koncept:** En **variabel** är som en låda där spelet sparar information. Ett **objekt** är en sak som har egna **variabler** (som position, färg osv) och kan göra saker. En **Sprite** är ett speciellt slags **objekt** som fungerar som en spelfigur.

**Instruktioner:** Hämta `||sprites:set mySprite to sprite [ ] of kind Player||` och lägg det i `||loops:on start||`. Klicka på ordet `mySprite`, välj **Rename variable...** och byt namn till **hero**. Klicka på den grå rutan för att rita din gubbe.
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

**Kort förklaring:** Koden skapar din figur. **Variabeln** som heter `hero` hjälper spelet att hålla koll på exakt vilket **objekt** (din **Sprite**) som är din huvudperson.

## Steg 2: Koordinater (X och Y)
**Koncept:** Skärmen är som ett osynligt rutnät. **X** bestämmer var figuren är i sidled, och **Y** bestämmer var den är i höjdled. Dessa värden kallas **koordinater**.

**Instruktioner:** Hämta `||sprites:set hero position to x [20] y [20]||` och sätt det under förra blocket. Ändra siffrorna för att flytta figuren.
```blocks
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(20, 20)
```

**Kort förklaring:** Din **Sprite** är ett **objekt**, vilket betyder att den kan minnas sina egna **X- och Y-koordinater**. Om du ändrar X och Y hoppar figuren direkt till den nya platsen.

## Steg 3: Flaggor och Egenskaper (Booleans)
**Koncept:** En **flagga** (eller **Boolean**) är en egenskap inuti ett **objekt** som fungerar som en strömbrytare – den kan bara vara På eller Av (sant eller falskt).

**Instruktioner:** Hämta `||sprites:set hero auto destroy [ON]||` och lägg det sist. Klicka på `auto destroy` och ändra till `show physics`.
```blocks
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
```

**Kort förklaring:** När du slår PÅ denna **flagga** visar spelet hemlig information om ditt **Sprite-objekt** direkt på skärmen, till exempel dess nuvarande **koordinater**.

## Steg 4: Input
**Koncept:** **Input** betyder inmatning, alltså att du skickar signaler med knapparna för att styra **objekten** i spelet.


**Instruktioner:** Hämta `||controller:move hero with buttons||` och lägg det sist i koden.
```blocks
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero)
```

**Kort förklaring:** Detta block talar om för spelet att det specifika **Sprite-objektet** som ligger i **variabeln** `hero` ska uppdatera sina **koordinater** när du ger spelet **input** (när du trycker på pilknapparna).

## Steg 5: Hastighet (vx och vy) och Parametrar
**Koncept:** Hastighet är hur snabbt figuren rör sig åt sidan (vx) eller upp och ner (vy). Siffrorna du skriver in i blocken för att bestämma detta kallas **parametrar**.

**Instruktioner:** Klicka på plustecknet **(+)** på blocket `||controller:move hero with buttons||`. Ändra siffrorna till **200** för både vx och vy.
```blocks
let hero: Sprite = null
hero = sprites.create(img`.`, SpriteKind.Player)
hero.setPosition(80, 60)
hero.setFlag(SpriteFlag.ShowPhysics, true)
controller.moveSprite(hero, 200, 200)
```

**Kort förklaring:** Genom att skriva in högre siffror (**parametrar**) ökar du hastigheten på din **Sprite** när den styrs av din **input**.