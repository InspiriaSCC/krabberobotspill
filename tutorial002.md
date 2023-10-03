### @activities true

```template
namespace myTiles {
    //% blockIdentity=images._tile
    export const tile0 = img`
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
    `
}
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    info.changeLifeBy(-1)
    sprites.destroy(otherSprite)
})
let krabbeRobot: Sprite = null
info.setLife(6)
scene.setBackgroundColor(9)
tiles.setTilemap(tiles.createTilemap(hex`2000200000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000002020000000000000000000000000000000000000000000000000000000000020202020000000000000000000000000000000000000000000000000000020202020202020200000000000000000000000000000000000000000000020202010101010102020200000000000000000000000000000000000202020202010101010101010101020000000000000000000000000000000202020101010101010101010101010102000000000000000000000000020202020101010101010101010101010101010200000000000000000000000002020202010101010101010101010101010101020000000000000000000000000000000202010101010101010101010101010202020000000000000000000000000000000202010101010101010101010101020202000000000000000000000000000000000202010101010101010101010202020200000000000000000000000000000000000202010101010101010101020000000000000000000000000000000000000000000202020101010101010102000000000000000000000000000000000000000000000002020101010101010202000000000000000000000000000000000000000002020201010101010101020200000000000000000000000000000000000000020101010101010101010102020000000000000000000000000000000000000002010101010101010101010102020000000000000000000000000000000002020201010101010101010101010202000000000000000000000000000000020202020201010101010101010101020000000000000000000000000000000202020202020101010101010101010202000000000000000000000000000000020202020202020101010101020202020000000000000000000000000000000002020202020202020202020202000000000000000000000000000000000000000002020202020202020202000000000000000000000000000000000000000000000002020202020202000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000`, img`
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
`, [myTiles.transparency16, sprites.castle.tileGrass1, sprites.castle.tilePath5], TileScale.Sixteen))
let mySprite = sprites.create(img`
    ....................8a8aa8a8....................
    .................aaa888aa8a8aaa.................
    ..............aaa8aa8a8aa888aa8aaa..............
    ...........8aa8aa8888a8aa8a8888aa8aa8...........
    ........8888aa8aa8aa8a8aa8a8aa8aa8aa8888........
    .....aaa8aa8aa8888aa8a8aa8a8aa8888aa8aa8aaa.....
    ...aa8888aa8aa8aa8aa888aa888aa8aa8aa8aa8888aa...
    dccaa8aa8aa8888aa8aa8a8aa8a8aa8aa8888aa8aa8aaccd
    bcb888aa8aa8aa8aa8aa8a8aa8a8aa8aa8aa8aa8aa888bcb
    dbbaa8aa8888aa8aa8888a8aa8a8888aa8aa8888aa8aabbd
    dbbaa8aa8aa8aa8888aa8a8aa8a8aa8888aa8aa8aa8aabbd
    dccaa8888aa8aa8aa8aa888aa888aa8aa8aa8aa8888aaccd
    bcbaa8aa8aa8888aa8aa8a8aa8a8aa8aa8888aa8aa8aabcb
    dbb888aa8aa8aa8aa8aa8a8aa8a8aa8aa8aa8aa8aa888bbd
    dbbaa8aa8888aa8aa8aa8a8aa8a8aa8aa8aa8888aa8aabbd
    dccaa8aa8aa8aa8aa8888a8aa8a8888aa8aa8aa8aa8aaccd
    bcbaa8888aa8aa8888aa888aa888aa8888aa8aa8888aabcb
    dbbaa8aa8aa8888aa8aa8a8aa8a8aa8aa8888aa8aa8aabbd
    dbb888aa8aa8aa8aa8aa8a8aa8a8aa8aa8aa8aa8aa888bbd
    dccaa8aa8888aa8aa8aa8a8aa8a8aa8aa8aa8888aa8aaccd
    bcbaa8aa8aa8aa8aa8aa888aa888aa8aa8aa8aa8aa8aabcb
    dbbaa8888aa8aa8aa888ccbbbbcc888aa8aa8aa8888aabbd
    dbbaa8aa8aa8aa888ccbbbbbbbbbbcc888aa8aa8aa8aabbd
    dcc888aa8aa888ccbbbbbccccccbbbbbcc888aa8aa888ccd
    bcbaa8aa888ccbbbbbccbddddddbccbbbbbcc888aa8aabcb
    dbbaa8aaccbbbbbccbddddddddddddbccbbbbbccaa8aabbd
    dbbaaccbbbbcccbddddddddddddddddddbcccbbbbccaabbd
    dcccbbbbcccbdddbccbbbbbbbbbbbbccbdddbcccbbbbcccd
    ccccccccbbbbbbbcbddddddddddddddbcbbbbbbbcccccccc
    bddddddddddddbcddddddddddddddddddcbddddddddddddb
    bbcbdddddddddcbd1111111111111111dbcdddddddddbcbb
    bbbcccccccccccd1bbbbbbbbbbbbbbbb1dcccccccccccbbb
    bbbbdddddddddc11beeeeeeeeeeeeeeb11cdddddddddbbbb
    bbb8aaaaaaa8dc1be3b33b33b33b33beb1cd8aaaaaaa8bbb
    bbb888888888dc1be3b33b33b33b33beb1cd888888888bbb
    bbb833333338dcbbf3b3effffffe33bebbcd833333338bbb
    bbb83ff3ff38dcbbf3bffffffffff3bebbcd83ff3ff38bbb
    bbb83cc3cc38dcbbf3effffffffffebebbcd83cc3cc38bbb
    bbb833333338dcbbf3eeeeeeeeeeeebebbcd833333338bbb
    cbb83ff3ff38dcbbe3b33b33b33b33bebbcd83ff3ff38bbc
    cbb83cc3cc38dcbbe3b33b33b33b33bebbcd83cc3cc38bbc
    ccbbbbbbbbbbdcbbe3b33b33b33feeeebbcdbbbbbbbbbbcc
    .cbbdddddddddcbbe3b33b33b33ffffebbcdddddddddbbc.
    ..cbdbbbdbbbdcbbf3b33b33b33f33febbcdbbbdbbbdbc..
    ...cdbbbdbbbdcbbf3b33b33b33bffeebbcdbbbdbbbdc...
    ....bddddddddcbbf3b33b33b33b33bebbcddddddddb....
    .....bdbbbdddcbbf3b33b33b33b33bebbcdddbbbdb.....
    ......bcccbbbcbbe3b33b33b33b33bebbcbbbcccb......
    `, SpriteKind.Food)
tiles.placeOnTile(mySprite, tiles.getTileLocation(15, 16))
let minRobot = sprites.create(img`
    ........................
    ...........bb...........
    ..........bbbb..........
    ........bbbbbbbb........
    .......bbbbbbbbbb.......
    .......bf2f33f2fb.......
    .......bbbb33bbbb.......
    ........babaabab........
    .........ab33ba.........
    ........babaabab........
    .....cbbbbbbbbbbbbc.....
    ....cbcbaaaaaaaabcbc....
    ...bbcbca666666acbcbb...
    ..b2bbc..a5555a..cbb2b..
    .5422b....a66a....b2245.
    .544b....bbaabb....b445.
    5555....bbb..bbb....5555
    55......ccc..ccc......55
    ........bbb..bbb........
    ........ccc..ccc........
    ........bbb..bbb........
    .......5424554245.......
    ........545..545........
    .........5....5.........
    `, SpriteKind.Player)
tiles.placeOnTile(minRobot, mySprite.tilemapLocation())
controller.moveSprite(minRobot)
scene.cameraFollowSprite(minRobot)
for (let index = 0; index < 4; index++) {
    krabbeRobot = sprites.create(img`
        . . . . . . 1 . . 1 . . . . . . 
        . . . . . 1 f 1 1 f 1 . . . . . 
        . . 2 2 . . 1 . . 1 . . 2 2 . . 
        . 2 . . 2 . 2 . . 2 . 2 . . 2 . 
        2 . 2 . . 2 2 2 2 2 2 . . 2 . 2 
        . 2 . 2 2 2 2 2 2 2 2 2 2 . 2 . 
        2 . . 2 2 2 2 2 2 2 2 2 2 . . 2 
        . . 2 . 2 2 2 2 2 2 2 2 . 2 . . 
        . 2 . 2 . 2 2 2 2 2 2 . 2 . 2 . 
        2 . . . 2 . . . . . . 2 . . . 2 
        . . 2 2 2 2 . . . . 2 2 2 2 . . 
        . . 2 2 2 . . . . . . 2 2 2 . . 
        . . . 2 2 2 2 . . 2 2 2 2 . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, SpriteKind.Enemy)
    tiles.placeOnRandomTile(krabbeRobot, assets.tile`transparency16`)
    krabbeRobot.follow(minRobot)
}

```

# Lag et spill om den store krabbekrigen
## Introduksjon
### Intro @unplugged

Professor K. Rabbe har laget en gigantisk hær av krabberoboter for å overta verden! Du og roboten din er alt som kan stoppe ham! Hjelp roboten din til å få kontroll på krabberobotene! Steg 1: Test spillet og se om du klarer å overleve første angrepsbølge!

### Steg 1: Test spillet!
Vi har laget litt ferdig kode for deg som utgangspunkt.
Du er på en øy i havet, og krabberobotene til professor K. Rabbe kan når som helst komme opp fra havet for å angripe deg.
Som du ser følger krabberobotene etter roboten din, og roboten kan ikke gjøre noe for å stoppe dem.
Du må lage feller som kan fange krabberobotene. Test spillet og se hva som skjer!
Når du har testet spillet, klikker du på ``||scene:Next||`` under for å lære hvordan du lager en teine! 

```blocks
namespace myTiles {
    //% blockIdentity=images._tile
    export const tile0 = img`
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
        . . . . . . . . . . . . . . . .
    `
}

}
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    info.changeLifeBy(-1)
    sprites.destroy(otherSprite)
})
let krabbeRobot: Sprite = null
info.setLife(6)
scene.setBackgroundColor(9)
tiles.setTilemap(tiles.createTilemap(hex`2000200000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000002020000000000000000000000000000000000000000000000000000000000020202020000000000000000000000000000000000000000000000000000020202020202020200000000000000000000000000000000000000000000020202010101010102020200000000000000000000000000000000000202020202010101010101010101020000000000000000000000000000000202020101010101010101010101010102000000000000000000000000020202020101010101010101010101010101010200000000000000000000000002020202010101010101010101010101010101020000000000000000000000000000000202010101010101010101010101010202020000000000000000000000000000000202010101010101010101010101020202000000000000000000000000000000000202010101010101010101010202020200000000000000000000000000000000000202010101010101010101020000000000000000000000000000000000000000000202020101010101010102000000000000000000000000000000000000000000000002020101010101010202000000000000000000000000000000000000000002020201010101010101020200000000000000000000000000000000000000020101010101010101010102020000000000000000000000000000000000000002010101010101010101010102020000000000000000000000000000000002020201010101010101010101010202000000000000000000000000000000020202020201010101010101010101020000000000000000000000000000000202020202020101010101010101010202000000000000000000000000000000020202020202020101010101020202020000000000000000000000000000000002020202020202020202020202000000000000000000000000000000000000000002020202020202020202000000000000000000000000000000000000000000000002020202020202000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000`, img`
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
`, [myTiles.transparency16, sprites.castle.tileGrass1, sprites.castle.tilePath5], TileScale.Sixteen))
let minRobot = sprites.create(img`
........................
...........bb...........
..........bbbb..........
........bbbbbbbb........
.......bbbbbbbbbb.......
.......bf2f33f2fb.......
.......bbbb33bbbb.......
........babaabab........
.........ab33ba.........
........babaabab........
.....cbbbbbbbbbbbbc.....
....cbcbaaaaaaaabcbc....
...bbcbca666666acbcbb...
..b2bbc..a5555a..cbb2b..
.5422b....a66a....b2245.
.544b....bbaabb....b445.
5555....bbb..bbb....5555
55......ccc..ccc......55
........bbb..bbb........
........ccc..ccc........
........bbb..bbb........
.......5424554245.......
........545..545........
.........5....5.........
`, SpriteKind.Player)
controller.moveSprite(minRobot)
scene.cameraFollowSprite(minRobot)
tiles.placeOnRandomTile(minRobot, sprites.castle.tileGrass1)
let mySprite = sprites.create(img`
....................8a8aa8a8....................
.................aaa888aa8a8aaa.................
..............aaa8aa8a8aa888aa8aaa..............
...........8aa8aa8888a8aa8a8888aa8aa8...........
........8888aa8aa8aa8a8aa8a8aa8aa8aa8888........
.....aaa8aa8aa8888aa8a8aa8a8aa8888aa8aa8aaa.....
...aa8888aa8aa8aa8aa888aa888aa8aa8aa8aa8888aa...
dccaa8aa8aa8888aa8aa8a8aa8a8aa8aa8888aa8aa8aaccd
bcb888aa8aa8aa8aa8aa8a8aa8a8aa8aa8aa8aa8aa888bcb
dbbaa8aa8888aa8aa8888a8aa8a8888aa8aa8888aa8aabbd
dbbaa8aa8aa8aa8888aa8a8aa8a8aa8888aa8aa8aa8aabbd
dccaa8888aa8aa8aa8aa888aa888aa8aa8aa8aa8888aaccd
bcbaa8aa8aa8888aa8aa8a8aa8a8aa8aa8888aa8aa8aabcb
dbb888aa8aa8aa8aa8aa8a8aa8a8aa8aa8aa8aa8aa888bbd
dbbaa8aa8888aa8aa8aa8a8aa8a8aa8aa8aa8888aa8aabbd
dccaa8aa8aa8aa8aa8888a8aa8a8888aa8aa8aa8aa8aaccd
bcbaa8888aa8aa8888aa888aa888aa8888aa8aa8888aabcb
dbbaa8aa8aa8888aa8aa8a8aa8a8aa8aa8888aa8aa8aabbd
dbb888aa8aa8aa8aa8aa8a8aa8a8aa8aa8aa8aa8aa888bbd
dccaa8aa8888aa8aa8aa8a8aa8a8aa8aa8aa8888aa8aaccd
bcbaa8aa8aa8aa8aa8aa888aa888aa8aa8aa8aa8aa8aabcb
dbbaa8888aa8aa8aa888ccbbbbcc888aa8aa8aa8888aabbd
dbbaa8aa8aa8aa888ccbbbbbbbbbbcc888aa8aa8aa8aabbd
dcc888aa8aa888ccbbbbbccccccbbbbbcc888aa8aa888ccd
bcbaa8aa888ccbbbbbccbddddddbccbbbbbcc888aa8aabcb
dbbaa8aaccbbbbbccbddddddddddddbccbbbbbccaa8aabbd
dbbaaccbbbbcccbddddddddddddddddddbcccbbbbccaabbd
dcccbbbbcccbdddbccbbbbbbbbbbbbccbdddbcccbbbbcccd
ccccccccbbbbbbbcbddddddddddddddbcbbbbbbbcccccccc
bddddddddddddbcddddddddddddddddddcbddddddddddddb
bbcbdddddddddcbd1111111111111111dbcdddddddddbcbb
bbbcccccccccccd1bbbbbbbbbbbbbbbb1dcccccccccccbbb
bbbbdddddddddc11beeeeeeeeeeeeeeb11cdddddddddbbbb
bbb8aaaaaaa8dc1be3b33b33b33b33beb1cd8aaaaaaa8bbb
bbb888888888dc1be3b33b33b33b33beb1cd888888888bbb
bbb833333338dcbbf3b3effffffe33bebbcd833333338bbb
bbb83ff3ff38dcbbf3bffffffffff3bebbcd83ff3ff38bbb
bbb83cc3cc38dcbbf3effffffffffebebbcd83cc3cc38bbb
bbb833333338dcbbf3eeeeeeeeeeeebebbcd833333338bbb
cbb83ff3ff38dcbbe3b33b33b33b33bebbcd83ff3ff38bbc
cbb83cc3cc38dcbbe3b33b33b33b33bebbcd83cc3cc38bbc
ccbbbbbbbbbbdcbbe3b33b33b33feeeebbcdbbbbbbbbbbcc
.cbbdddddddddcbbe3b33b33b33ffffebbcdddddddddbbc.
..cbdbbbdbbbdcbbf3b33b33b33f33febbcdbbbdbbbdbc..
...cdbbbdbbbdcbbf3b33b33b33bffeebbcdbbbdbbbdc...
....bddddddddcbbf3b33b33b33b33bebbcddddddddb....
.....bdbbbdddcbbf3b33b33b33b33bebbcdddbbbdb.....
......bcccbbbcbbe3b33b33b33b33bebbcbbbcccb......
`, SpriteKind.Food)
tiles.placeOnTile(mySprite, tiles.getTileLocation(15, 16))
for (let index = 0; index < 4; index++) {
    krabbeRobot = sprites.create(img`
. . . . . . 1 . . 1 . . . . . . 
. . . . . 1 f 1 1 f 1 . . . . . 
. . 2 2 . . 1 . . 1 . . 2 2 . . 
. 2 . . 2 . 2 . . 2 . 2 . . 2 . 
2 . 2 . . 2 2 2 2 2 2 . . 2 . 2 
. 2 . 2 2 2 2 2 2 2 2 2 2 . 2 . 
2 . . 2 2 2 2 2 2 2 2 2 2 . . 2 
. . 2 . 2 2 2 2 2 2 2 2 . 2 . . 
. 2 . 2 . 2 2 2 2 2 2 . 2 . 2 . 
2 . . . 2 . . . . . . 2 . . . 2 
. . 2 2 2 2 . . . . 2 2 2 2 . . 
. . 2 2 2 . . . . . . 2 2 2 . . 
. . . 2 2 2 2 . . 2 2 2 2 . . . 
. . . . . . . . . . . . . . . . 
. . . . . . . . . . . . . . . . 
. . . . . . . . . . . . . . . . 
`, SpriteKind.Enemy)
    tiles.placeOnRandomTile(krabbeRobot, assets.tile`transparency16`)
    krabbeRobot.follow(minRobot)
}
```

### Steg 2 Legg feller ved å trykke på en knapp!
Roboten din skal legge feller ved at du trykker på knapp A. Da trenger du blokken ``||controller:on A button pressed||``. Hent den fra ``||controller:Controller||``-menyen og plasser den ved siden av koden din.
Klikk på ``||scene:Next||`` for å gå videre.


``` blocks
// @highlight
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
	
})
```
### Steg 3 Lag en teine-sprite
Inni blokken du la sist skal vi lage en sprite.
En sprite er et lite, interaktivt bilde som kan plasseres rundt i spillverdenen, akkurat som krabberobotene og roboten du kontrollerer.
Hent en den røde blokken ``||variables:set mySprite2 to sprite of kind Player||`` fra ``||sprites:Sprites||``-menyen. Klikk på ``||scene:Next||`` når du er ferdig.

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    // @highlight
    mySprite2 = sprites.create(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, SpriteKind.Player)
})
```

### Teiner @unplugged
En teine er en boks av netting til å fange fisk eller krepsdyr i.
Boksen er laget av materialer som tåler saltvann over tid, og inni boksen legger man agn som lokker til seg dyrene man vil fange.
Den har åpninger som er sånn at dyrene finner veien inn, men de kommer seg ikke ut igjen.
I tillegg har den dører som du kan åpne for å få tak i fangsten.
Slike feller er veldig effektive for å fange krabber.

### Steg 4 Tegn teine-Spriten
Klikk på det grå kvadratet i ``||sprites:set mySprite2 to sprite of kind Player||``-blokken og tegn en firkant eller en boks ved å bruke tegneverktøyet i sprite-editoren.
Sprite-editoren er en programsnutt som lar deg tegne og redigere sprites.
Om du vil gjøre det enkelt, tegner du bare et firkant. (tips: Jo større du tegner teinen, jo lettere blir spillet!)
Ikke glem å trykke på ``||loops:Done||``-knappen nede i høyre hjørne av editoren når du er ferdig.
Klikk på ordet ``||variables:mySprite2||`` i ``||variables:set mySprite2 to sprite of kind player||``-blokken og velg ``||variables:Rename variable||``. Skriv inn ``||variables:teine||`` og trykk på ``||loops:Ok||``.
Klikk på ordet ``||sprites:Player||`` i ``||variables:set mySprite2 to sprite of kind Player||``-blokken og velg ``||sprites:Add a new kind||``. Skriv inn ``||sprites:Felle||`` og trykk på ``||loops:Ok||``.
Klikk på ``||scene:Next||`` når du er fornøyd.

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    // @highlight
    teine = sprites.create(img`
        . . . . . . f f f f f f f f f f 
        . . . . . f f . 1 . 1 . 1 . f f 
        . . . . f 1 f 1 . 1 . 1 . f . f 
        . . . f 1 . f . 1 . 1 . f . 1 f 
        . . f 1 . 1 f 1 . 1 . f . 1 . f 
        . f 1 . 1 . f . 1 . f . 1 . 1 f 
        f f f f f f f f f f . 1 . 1 . f 
        f . 1 . 1 . f . f f 1 . 1 . 1 f 
        f 1 . 1 . 1 f f . f . 1 . 1 . f 
        f . 1 . 1 . f f f f f f f f f f 
        f 1 . 1 . f . 1 . f 1 . 1 . f . 
        f . 1 . f . 1 . 1 f . 1 . f . . 
        f 1 . f . 1 . 1 . f 1 . f . . . 
        f . f . 1 . 1 . 1 f . f . . . . 
        f f . 1 . 1 . 1 . f f . . . . . 
        f f f f f f f f f f . . . . . . 
        `, SpriteKind.Felle)
})
```
### Steg 5 Plassere teiner 1
Foreløpig skjer det ikke noe når du trykker på A.
For å plassere ut en felle der roboten din er, trenger du blokken ``||scene:place mySprite on top of tilemap col 0 row 0||``.
Hent den fra ``||scene:Scene||``-menyen og plasser den inne i ``||controller:on A button pressed||``-blokken under resten av koden din.
Klikk ``||scene:Next||`` for å gå videre!

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    teine = sprites.create(img`
        . . . . . . f f f f f f f f f f 
        . . . . . f f . 1 . 1 . 1 . f f 
        . . . . f 1 f 1 . 1 . 1 . f . f 
        . . . f 1 . f . 1 . 1 . f . 1 f 
        . . f 1 . 1 f 1 . 1 . f . 1 . f 
        . f 1 . 1 . f . 1 . f . 1 . 1 f 
        f f f f f f f f f f . 1 . 1 . f 
        f . 1 . 1 . f . f f 1 . 1 . 1 f 
        f 1 . 1 . 1 f f . f . 1 . 1 . f 
        f . 1 . 1 . f f f f f f f f f f 
        f 1 . 1 . f . 1 . f 1 . 1 . f . 
        f . 1 . f . 1 . 1 f . 1 . f . . 
        f 1 . f . 1 . 1 . f 1 . f . . . 
        f . f . 1 . 1 . 1 f . f . . . . 
        f f . 1 . 1 . 1 . f f . . . . . 
        f f f f f f f f f f . . . . . . 
        `, SpriteKind.Felle)
    // @highlight
    tiles.placeOnTile(mySprite, tiles.getTileLocation(0, 0))
})
```



### Steg 6 Plassere teiner 2
Nå trenger du den ovale blokken ``||scene:tilemapLocation of mySprite||`` fra ``||scene:Scene||``-menyen.
Dra den inn i det ovale feltet der det står ``||scene:tilemap col 0 row 0||``, slik at den erstatter det som står der.
Pass på at ``||scene:tilemapLocation of mySprite||`` erstatter hele den store ``||scene:tilemap col 0 row 0||``-ovalen, og at den ikke havner i et av de små feltene med tall.
Klikk ``||scene:Next||`` når du har fått det til.

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    teine = sprites.create(img`
        . . . . . . f f f f f f f f f f 
        . . . . . f f . 1 . 1 . 1 . f f 
        . . . . f 1 f 1 . 1 . 1 . f . f 
        . . . f 1 . f . 1 . 1 . f . 1 f 
        . . f 1 . 1 f 1 . 1 . f . 1 . f 
        . f 1 . 1 . f . 1 . f . 1 . 1 f 
        f f f f f f f f f f . 1 . 1 . f 
        f . 1 . 1 . f . f f 1 . 1 . 1 f 
        f 1 . 1 . 1 f f . f . 1 . 1 . f 
        f . 1 . 1 . f f f f f f f f f f 
        f 1 . 1 . f . 1 . f 1 . 1 . f . 
        f . 1 . f . 1 . 1 f . 1 . f . . 
        f 1 . f . 1 . 1 . f 1 . f . . . 
        f . f . 1 . 1 . 1 f . f . . . . 
        f f . 1 . 1 . 1 . f f . . . . . 
        f f f f f f f f f f . . . . . . 
        `, SpriteKind.Felle)
    // @highlight
    tiles.placeOnTile(mySprite, mySprite.tilemapLocation())
})

```

### Steg 7 Plassere teiner 3
Du må gjøre enda noen endringer i de siste blokkene. Først må du endre den første ``||variables:mySprite||`` til ``||variables:teine||`` ved å trykke på ``||variables:mySprite||`` i ``||scene:place mySprite on top of tilemapLocation of mySprite||``-blokken og velge ``||variables:teine||``.
Klikk på lyspæren om du er usikker på hvilken ``||variables:mySprite||`` som skal endres.
Når du har gjort det, trykker du på ``||scene:Next||``.

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    teine = sprites.create(img`
        . . . . . . f f f f f f f f f f 
        . . . . . f f . 1 . 1 . 1 . f f 
        . . . . f 1 f 1 . 1 . 1 . f . f 
        . . . f 1 . f . 1 . 1 . f . 1 f 
        . . f 1 . 1 f 1 . 1 . f . 1 . f 
        . f 1 . 1 . f . 1 . f . 1 . 1 f 
        f f f f f f f f f f . 1 . 1 . f 
        f . 1 . 1 . f . f f 1 . 1 . 1 f 
        f 1 . 1 . 1 f f . f . 1 . 1 . f 
        f . 1 . 1 . f f f f f f f f f f 
        f 1 . 1 . f . 1 . f 1 . 1 . f . 
        f . 1 . f . 1 . 1 f . 1 . f . . 
        f 1 . f . 1 . 1 . f 1 . f . . . 
        f . f . 1 . 1 . 1 f . f . . . . 
        f f . 1 . 1 . 1 . f f . . . . . 
        f f f f f f f f f f . . . . . . 
        `, SpriteKind.Felle)
    // @highlight
    tiles.placeOnTile(teine, mySprite.tilemapLocation())
})
```
### Steg 8 Plassere teiner 4
Nå må du endre den andre ``||variables:mySprite||`` til ``||variables:minRobot||`` ved å klikke på den og velge ``||variables:minRobot||``.
Test spillet og sjekk om roboten din legger feller!
Klikk ``||scene:Next||`` for å gå videre.

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    teine = sprites.create(img`
        . . . . . . f f f f f f f f f f 
        . . . . . f f . 1 . 1 . 1 . f f 
        . . . . f 1 f 1 . 1 . 1 . f . f 
        . . . f 1 . f . 1 . 1 . f . 1 f 
        . . f 1 . 1 f 1 . 1 . f . 1 . f 
        . f 1 . 1 . f . 1 . f . 1 . 1 f 
        f f f f f f f f f f . 1 . 1 . f 
        f . 1 . 1 . f . f f 1 . 1 . 1 f 
        f 1 . 1 . 1 f f . f . 1 . 1 . f 
        f . 1 . 1 . f f f f f f f f f f 
        f 1 . 1 . f . 1 . f 1 . 1 . f . 
        f . 1 . f . 1 . 1 f . 1 . f . . 
        f 1 . f . 1 . 1 . f 1 . f . . . 
        f . f . 1 . 1 . 1 f . f . . . . 
        f f . 1 . 1 . 1 . f f . . . . . 
        f f f f f f f f f f . . . . . . 
        `, SpriteKind.Felle)
    // @highlight
    tiles.placeOnTile(teine, minRobot.tilemapLocation())
})

```

### Steg 9 Fange krabberobotene 1
Nå som du kan legge feller, må du få krabbene til å forsvinne når de går i en felle.
Til det trenger du først en ``||sprites:on sprite of kind Player overlaps otherSprite of kind Player||``-blokk fra ``||sprites:Sprites||``-menyen.
Hent en og legg den ved siden av resten av koden din.
Klikk ``||scene:Next||`` når du har fått blokken ut på arbeidsbordet.

```blocks
// @highlight
sprites.onOverlap(SpriteKind.Player, SpriteKind.Player, function (sprite, otherSprite) {
	
})
```

### Steg 10 Fange krabberobotene 2
Nå kan du snart få krabbene til å bli borte når de går i fella, men først trenger du en ``||sprites:destroy mySprite||``-blokk.
Hent en fra ``||sprites:Sprites||``-menyen og legg den inn i ``||sprites:on sprite of kind Player overlaps otherSprite of kind Player||``-blokken.
Klikk ``||scene:Next||`` når du har gjort det.

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Player, function (sprite, otherSprite) {
    // @highlight
    sprites.destroy(mySprite)
})
```

### Steg 11 Fange krabberobotene 3
Du må gjøre noen endringer i ``||sprites:on sprite of kind Player overlaps othersprite of kind Player||``-blokken for at alt skal fungere som tenkt.
Blokken sier noe om to sprites, ``||variables:sprite||`` og ``||variables:otherSprite||``.
Foreløpig er begge disse av typen ``||sprites:Player||``. Nå skal du endre typen sprite for begge.
Den første, som heter ``||variables:sprite||``, skal være av typen ``||sprites:Felle||``.
Klikk på ordet ``||sprites:Player||`` etter ordet ``||variables:sprite||`` og velg ``||sprites:Felle||`` fra menyen som dukker opp.
Så klikker du på ordet ``||sprites:Player||`` etter ordet ``||variables:otherSprite||`` og velger ``||sprites:Enemy||``.
Klikk ``||scene:Next||`` når begge sprite-typene er endret.

```blocks
// @highlight
sprites.onOverlap(SpriteKind.Felle, SpriteKind.Enemy, function (sprite, otherSprite) {
    sprites.destroy(mySprite)
})
```

### Steg 12 Fange krabberobotene 4
Siden det kun er teinene du legger ut som er sprites av typen "Felle", vil spriten som blokken kaller ``||variables:sprite||`` alltid være en teine,
og siden det kun er krabberobotene som er av typen "Enemy", vil spriten ``||variables:otherSprite||`` alltid være en krabberobot.
For at krabberoboten skal bli borte, må vi få blokken ``||sprites:destroy mySprite||`` til å ødelegge ``||variables:otherSprite||``.
Klikk på ovalen der det står ``||variables:otherSprite||`` i ``||sprites:on sprite of kind Felle overlaps othersprite of kind Enemy||``-blokken og dra den ned i feltet der det står ``||variables:mySprite||`` i blokken ``||sprites:destroy mySprite||``, slik at det står ``||variables:otherSprite||`` der.
Test spillet og sjekk at krabberobotene blir borte når de går i en teine.
Klikk ``||scene:Next||`` for å komme videre.

```blocks
sprites.onOverlap(SpriteKind.Felle, SpriteKind.Enemy, function (sprite, otherSprite) {
    // @highlight
    sprites.destroy(otherSprite)
})
```

### Steg 13 Få poeng
For å få poeng hver gang du fanger en krabberobot, trenger du en blokk som heter ``||info:change score by 1||`` fra ``||info:Info||``-menyen.
Hent den og legg den inn nederst i ``||sprites:on sprite of kind Felle overlaps othersprite of kind Enemy||``-blokken.
Nå får du et poeng for hver krabberobot som går i fella.
Test spillet før du klikker ``||scene:Next||``.

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    // @highlight
    sprites.destroy(otherSprite)
    info.changeScoreBy(1)
})
```

### Spøkelsesteiner @unplugged 
Krabbeteiner, krepseteiner og hummerteiner som blir mistet, blir liggende på havbunnen.
Siden de ofte er laget av plast eller andre materialer som ikke brytes ned, fortsetter de å fange dyr så lenge de blir liggende.
Da kalles de spøkelsesteiner.
På nye teiner er det krav om at de må være laget slik at de åpnes når de blir liggende lenge, slik at dyr som går i fella lett kan rømme.

### Steg 14 Fjerne brukte teiner
Som du ser blir teinene du slipper liggende på spillebrettet for alltid, akkurat som spøkelsesteiner i virkeligheten.
For å gjøre teinene litt mer miljøvennlige, skal du få dem til å teleportere bort etter et halvt sekund.
Det må du gjøre i den samme blokken med kode som du brukte for å lage teinene, ``||controller:on A button pressed||``-blokken, så du må legge til litt mer kode der.
Du trenger to blokker, ``||loops:pause 100 ms||`` fra ``||loops:Loops||``-menyen og ``||sprites:destroy mySprite||`` fra ``||sprites:Sprites||`` menyen.
Hent dem og legg dem inn i ``||controller:on A button pressed||``-blokken under ``||scene:place teine on top of tilemapLocation of minRobot||``.`
Klikk på ``||scene:Next||`` når du er ferdig.

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    teine = sprites.create(img`
        . . . . . . f f f f f f f f f f 
        . . . . . f f . 1 . 1 . 1 . f f 
        . . . . f 1 f 1 . 1 . 1 . f . f 
        . . . f 1 . f . 1 . 1 . f . 1 f 
        . . f 1 . 1 f 1 . 1 . f . 1 . f 
        . f 1 . 1 . f . 1 . f . 1 . 1 f 
        f f f f f f f f f f . 1 . 1 . f 
        f . 1 . 1 . f . f f 1 . 1 . 1 f 
        f 1 . 1 . 1 f f . f . 1 . 1 . f 
        f . 1 . 1 . f f f f f f f f f f 
        f 1 . 1 . f . 1 . f 1 . 1 . f . 
        f . 1 . f . 1 . 1 f . 1 . f . . 
        f 1 . f . 1 . 1 . f 1 . f . . . 
        f . f . 1 . 1 . 1 f . f . . . . 
        f f . 1 . 1 . 1 . f f . . . . . 
        f f f f f f f f f f . . . . . . 
        `, SpriteKind.Felle)
    tiles.placeOnTile(teine, minRobot.tilemapLocation())
    //@highlight
    pause(100)
    //@highlight
    sprites.destroy(mySprite)
})
```

### Steg 15 Bestem hvor lenge teinene skal ligge på spillebrettet
Det trengs et par endringer på de to siste blokkene du brukte.
Endre 100 ms til 500 ms i ``||loops:pause 100 ms||``-blokken, og endre ``||variables:mySprite||`` til ``||variables:teine||`` i ``||sprites:destroy mySprite||``-blokken.
Nå kan du bare legge én og én teine, og hver teine varer bare i et halvt sekund før den fteleporteres bort, og du kan legge ut den neste.
Klikk ``||scene:Next||`` for å gå videre.

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    teine = sprites.create(img`
        . . . . . . f f f f f f f f f f 
        . . . . . f f . 1 . 1 . 1 . f f 
        . . . . f 1 f 1 . 1 . 1 . f . f 
        . . . f 1 . f . 1 . 1 . f . 1 f 
        . . f 1 . 1 f 1 . 1 . f . 1 . f 
        . f 1 . 1 . f . 1 . f . 1 . 1 f 
        f f f f f f f f f f . 1 . 1 . f 
        f . 1 . 1 . f . f f 1 . 1 . 1 f 
        f 1 . 1 . 1 f f . f . 1 . 1 . f 
        f . 1 . 1 . f f f f f f f f f f 
        f 1 . 1 . f . 1 . f 1 . 1 . f . 
        f . 1 . f . 1 . 1 f . 1 . f . . 
        f 1 . f . 1 . 1 . f 1 . f . . . 
        f . f . 1 . 1 . 1 f . f . . . . 
        f f . 1 . 1 . 1 . f f . . . . . 
        f f f f f f f f f f . . . . . . 
        `, SpriteKind.Felle)
    tiles.placeOnTile(teine, minRobot.tilemapLocation())
    // @highlight
    pause(500)
    // @highlight
    sprites.destroy(teine)
    ```

### Steg 16 Gjøre spillet vanskeligere.
Du kan nå gjøre spillet vanskeligere på flere måter. Du kan for eksempel starte med mange flere krabberoboter.
Om du endrer tallet 4 øverst i den grønne ``||loops:repeat 4 times||``-blokken til et høyere tall, lages det like mange krabberoboter som tallet du setter inn.
Klarer du å overleve 25 krabberoboter? Endre tallet til 25 og test! Er 25 for mange? Test med færre!
klikk ``||scene:Next||`` når du har testet noen ganger.

```blocks
// @highlight
for (let index = 0; index < 25; index++) {
    krabbeRobot = sprites.create(img`
        . . . . . . 1 . . 1 . . . . . . 
        . . . . . 1 f 1 1 f 1 . . . . . 
        . . 2 2 . . 1 . . 1 . . 2 2 . . 
        . 2 . . 2 . 2 . . 2 . 2 . . 2 . 
        2 . 2 . . 2 2 2 2 2 2 . . 2 . 2 
        . 2 . 2 2 2 2 2 2 2 2 2 2 . 2 . 
        2 . . 2 2 2 2 2 2 2 2 2 2 . . 2 
        . . 2 . 2 2 2 2 2 2 2 2 . 2 . . 
        . 2 . 2 . 2 2 2 2 2 2 . 2 . 2 . 
        2 . . . 2 . . . . . . 2 . . . 2 
        . . 2 2 2 2 . . . . 2 2 2 2 . . 
        . . 2 2 2 . . . . . . 2 2 2 . . 
        . . . 2 2 2 2 . . 2 2 2 2 . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, SpriteKind.Enemy)
    tiles.placeOnRandomTile(krabbeRobot, assets.tile`transparency16`)
    krabbeRobot.follow(minRobot)
}
```

### Steg 17 Angrepsbølger 1
Du kan gjøre spillet vanskeligere på en litt morsommere måte ved å la krabberobotene angripe i stadig større antall, i stedet for at alle kommer etter deg på en gang.
Til det trenger du først en ``||loops:forever||``-blokk fra ``||loops:Loops||``-menyen. Hent en og legg den for seg selv ved siden av hovedkoden din.
Klikk ``||scene:Next||`` for å gå videre.

```blocks
forever(function () {
	
})
```

### Steg 18 Angrepsbølger 2
Nå skal løkken som lager krabberobotene settes inn i denne ``||loops:forever||``-løkken.
Klikk på den grønne ``||loops:repeat 25 times||``-løkken og dra den inn i ``||loops:forever||``-løkken.
Endre tallet som står i ``||loops:repeat 25 times||``-løkken til 0, ellers kræsjer du spillet, for den kommer til å lage uendelig mange krabber ellers.
Du kan klikke på lyspæren for å se hvordan hovedkoden og ``||loops:forever||``-løkken skal se ut. Klikk ``||scene:Next||`` når du har fått det til.

```blocks
let krabbeRobot: Sprite = null
info.setLife(100)
scene.setBackgroundColor(9)
tiles.setTilemap(tiles.createTilemap(hex`2000200000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000002020000000000000000000000000000000000000000000000000000000000020202020000000000000000000000000000000000000000000000000000020202020202020200000000000000000000000000000000000000000000020202010101010102020200000000000000000000000000000000000202020202010101010101010101020000000000000000000000000000000202020101010101010101010101010102000000000000000000000000020202020101010101010101010101010101010200000000000000000000000002020202010101010101010101010101010101020000000000000000000000000000000202010101010101010101010101010202020000000000000000000000000000000202010101010101010101010101020202000000000000000000000000000000000202010101010101010101010202020200000000000000000000000000000000000202010101010101010101020000000000000000000000000000000000000000000202020101010101010102000000000000000000000000000000000000000000000002020101010101010202000000000000000000000000000000000000000002020201010101010101020200000000000000000000000000000000000000020101010101010101010102020000000000000000000000000000000000000002010101010101010101010102020000000000000000000000000000000002020201010101010101010101010202000000000000000000000000000000020202020201010101010101010101020000000000000000000000000000000202020202020101010101010101010202000000000000000000000000000000020202020202020101010101020202020000000000000000000000000000000002020202020202020202020202000000000000000000000000000000000000000002020202020202020202000000000000000000000000000000000000000000000002020202020202000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000`, img`
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
`, [myTiles.transparency16, sprites.castle.tileGrass1, sprites.castle.tilePath5], TileScale.Sixteen))
let mySprite = sprites.create(img`
    ....................8a8aa8a8....................
    .................aaa888aa8a8aaa.................
    ..............aaa8aa8a8aa888aa8aaa..............
    ...........8aa8aa8888a8aa8a8888aa8aa8...........
    ........8888aa8aa8aa8a8aa8a8aa8aa8aa8888........
    .....aaa8aa8aa8888aa8a8aa8a8aa8888aa8aa8aaa.....
    ...aa8888aa8aa8aa8aa888aa888aa8aa8aa8aa8888aa...
    dccaa8aa8aa8888aa8aa8a8aa8a8aa8aa8888aa8aa8aaccd
    bcb888aa8aa8aa8aa8aa8a8aa8a8aa8aa8aa8aa8aa888bcb
    dbbaa8aa8888aa8aa8888a8aa8a8888aa8aa8888aa8aabbd
    dbbaa8aa8aa8aa8888aa8a8aa8a8aa8888aa8aa8aa8aabbd
    dccaa8888aa8aa8aa8aa888aa888aa8aa8aa8aa8888aaccd
    bcbaa8aa8aa8888aa8aa8a8aa8a8aa8aa8888aa8aa8aabcb
    dbb888aa8aa8aa8aa8aa8a8aa8a8aa8aa8aa8aa8aa888bbd
    dbbaa8aa8888aa8aa8aa8a8aa8a8aa8aa8aa8888aa8aabbd
    dccaa8aa8aa8aa8aa8888a8aa8a8888aa8aa8aa8aa8aaccd
    bcbaa8888aa8aa8888aa888aa888aa8888aa8aa8888aabcb
    dbbaa8aa8aa8888aa8aa8a8aa8a8aa8aa8888aa8aa8aabbd
    dbb888aa8aa8aa8aa8aa8a8aa8a8aa8aa8aa8aa8aa888bbd
    dccaa8aa8888aa8aa8aa8a8aa8a8aa8aa8aa8888aa8aaccd
    bcbaa8aa8aa8aa8aa8aa888aa888aa8aa8aa8aa8aa8aabcb
    dbbaa8888aa8aa8aa888ccbbbbcc888aa8aa8aa8888aabbd
    dbbaa8aa8aa8aa888ccbbbbbbbbbbcc888aa8aa8aa8aabbd
    dcc888aa8aa888ccbbbbbccccccbbbbbcc888aa8aa888ccd
    bcbaa8aa888ccbbbbbccbddddddbccbbbbbcc888aa8aabcb
    dbbaa8aaccbbbbbccbddddddddddddbccbbbbbccaa8aabbd
    dbbaaccbbbbcccbddddddddddddddddddbcccbbbbccaabbd
    dcccbbbbcccbdddbccbbbbbbbbbbbbccbdddbcccbbbbcccd
    ccccccccbbbbbbbcbddddddddddddddbcbbbbbbbcccccccc
    bddddddddddddbcddddddddddddddddddcbddddddddddddb
    bbcbdddddddddcbd1111111111111111dbcdddddddddbcbb
    bbbcccccccccccd1bbbbbbbbbbbbbbbb1dcccccccccccbbb
    bbbbdddddddddc11beeeeeeeeeeeeeeb11cdddddddddbbbb
    bbb8aaaaaaa8dc1be3b33b33b33b33beb1cd8aaaaaaa8bbb
    bbb888888888dc1be3b33b33b33b33beb1cd888888888bbb
    bbb833333338dcbbf3b3effffffe33bebbcd833333338bbb
    bbb83ff3ff38dcbbf3bffffffffff3bebbcd83ff3ff38bbb
    bbb83cc3cc38dcbbf3effffffffffebebbcd83cc3cc38bbb
    bbb833333338dcbbf3eeeeeeeeeeeebebbcd833333338bbb
    cbb83ff3ff38dcbbe3b33b33b33b33bebbcd83ff3ff38bbc
    cbb83cc3cc38dcbbe3b33b33b33b33bebbcd83cc3cc38bbc
    ccbbbbbbbbbbdcbbe3b33b33b33feeeebbcdbbbbbbbbbbcc
    .cbbdddddddddcbbe3b33b33b33ffffebbcdddddddddbbc.
    ..cbdbbbdbbbdcbbf3b33b33b33f33febbcdbbbdbbbdbc..
    ...cdbbbdbbbdcbbf3b33b33b33bffeebbcdbbbdbbbdc...
    ....bddddddddcbbf3b33b33b33b33bebbcddddddddb....
    .....bdbbbdddcbbf3b33b33b33b33bebbcdddbbbdb.....
    ......bcccbbbcbbe3b33b33b33b33bebbcbbbcccb......
    `, SpriteKind.Food)
tiles.placeOnTile(mySprite, tiles.getTileLocation(15, 16))
let minRobot = sprites.create(img`
    ........................
    ...........bb...........
    ..........bbbb..........
    ........bbbbbbbb........
    .......bbbbbbbbbb.......
    .......bf2f33f2fb.......
    .......bbbb33bbbb.......
    ........babaabab........
    .........ab33ba.........
    ........babaabab........
    .....cbbbbbbbbbbbbc.....
    ....cbcbaaaaaaaabcbc....
    ...bbcbca666666acbcbb...
    ..b2bbc..a5555a..cbb2b..
    .5422b....a66a....b2245.
    .544b....bbaabb....b445.
    5555....bbb..bbb....5555
    55......ccc..ccc......55
    ........bbb..bbb........
    ........ccc..ccc........
    ........bbb..bbb........
    .......5424554245.......
    ........545..545........
    .........5....5.........
    `, SpriteKind.Player)
tiles.placeOnTile(minRobot, mySprite.tilemapLocation())
controller.moveSprite(minRobot)
scene.cameraFollowSprite(minRobot)
forever(function () {
    // @highlight
    for (let index = 0; index < 0; index++) {
        // @highlight
        krabbeRobot = sprites.create(img`
            . . . . . . 1 . . 1 . . . . . . 
            . . . . . 1 f 1 1 f 1 . . . . . 
            . . 2 2 . . 1 . . 1 . . 2 2 . . 
            . 2 . . 2 . 2 . . 2 . 2 . . 2 . 
            2 . 2 . . 2 2 2 2 2 2 . . 2 . 2 
            . 2 . 2 2 2 2 2 2 2 2 2 2 . 2 . 
            2 . . 2 2 2 2 2 2 2 2 2 2 . . 2 
            . . 2 . 2 2 2 2 2 2 2 2 . 2 . . 
            . 2 . 2 . 2 2 2 2 2 2 . 2 . 2 . 
            2 . . . 2 . . . . . . 2 . . . 2 
            . . 2 2 2 2 . . . . 2 2 2 2 . . 
            . . 2 2 2 . . . . . . 2 2 2 . . 
            . . . 2 2 2 2 . . 2 2 2 2 . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            `, SpriteKind.Enemy)
        // @highlight
        tiles.placeOnRandomTile(krabbeRobot, assets.tile`transparency16`)
        // @highlight
        krabbeRobot.follow(minRobot)
    }
})
```

### Steg 19 Angrepsbølger 3

Krabberobotene skal angripe i voksende bølger, slik at for hvert angrep kommer det en krabberobot mer enn i forrige.
Til det trenger du en variabel. Klikk på ``||variables:Variables||``-menyen og velg ``||variables:Make a new variable||`` øverst. Gi den navnet ``||variables:krabbeAntall||``.
Nå har du fått noen nye blokker i ``||variables:Variables||``-menyen. Hent den som heter ``||variables:set krabbeAntall to 0||`` og sett den inn øverst i hovedkoden.

```blocks
info.setLife(6)
scene.setBackgroundColor(9)
tiles.setTilemap(tiles.createTilemap(hex`2000200000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000002020000000000000000000000000000000000000000000000000000000000020202020000000000000000000000000000000000000000000000000000020202020202020200000000000000000000000000000000000000000000020202010101010102020200000000000000000000000000000000000202020202010101010101010101020000000000000000000000000000000202020101010101010101010101010102000000000000000000000000020202020101010101010101010101010101010200000000000000000000000002020202010101010101010101010101010101020000000000000000000000000000000202010101010101010101010101010202020000000000000000000000000000000202010101010101010101010101020202000000000000000000000000000000000202010101010101010101010202020200000000000000000000000000000000000202010101010101010101020000000000000000000000000000000000000000000202020101010101010102000000000000000000000000000000000000000000000002020101010101010202000000000000000000000000000000000000000002020201010101010101020200000000000000000000000000000000000000020101010101010101010102020000000000000000000000000000000000000002010101010101010101010102020000000000000000000000000000000002020201010101010101010101010202000000000000000000000000000000020202020201010101010101010101020000000000000000000000000000000202020202020101010101010101010202000000000000000000000000000000020202020202020101010101020202020000000000000000000000000000000002020202020202020202020202000000000000000000000000000000000000000002020202020202020202000000000000000000000000000000000000000000000002020202020202000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000`, img`
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
................................
`, [myTiles.transparency16, sprites.castle.tileGrass1, sprites.castle.tilePath5], TileScale.Sixteen))
let mySprite = sprites.create(img`
    ....................8a8aa8a8....................
    .................aaa888aa8a8aaa.................
    ..............aaa8aa8a8aa888aa8aaa..............
    ...........8aa8aa8888a8aa8a8888aa8aa8...........
    ........8888aa8aa8aa8a8aa8a8aa8aa8aa8888........
    .....aaa8aa8aa8888aa8a8aa8a8aa8888aa8aa8aaa.....
    ...aa8888aa8aa8aa8aa888aa888aa8aa8aa8aa8888aa...
    dccaa8aa8aa8888aa8aa8a8aa8a8aa8aa8888aa8aa8aaccd
    bcb888aa8aa8aa8aa8aa8a8aa8a8aa8aa8aa8aa8aa888bcb
    dbbaa8aa8888aa8aa8888a8aa8a8888aa8aa8888aa8aabbd
    dbbaa8aa8aa8aa8888aa8a8aa8a8aa8888aa8aa8aa8aabbd
    dccaa8888aa8aa8aa8aa888aa888aa8aa8aa8aa8888aaccd
    bcbaa8aa8aa8888aa8aa8a8aa8a8aa8aa8888aa8aa8aabcb
    dbb888aa8aa8aa8aa8aa8a8aa8a8aa8aa8aa8aa8aa888bbd
    dbbaa8aa8888aa8aa8aa8a8aa8a8aa8aa8aa8888aa8aabbd
    dccaa8aa8aa8aa8aa8888a8aa8a8888aa8aa8aa8aa8aaccd
    bcbaa8888aa8aa8888aa888aa888aa8888aa8aa8888aabcb
    dbbaa8aa8aa8888aa8aa8a8aa8a8aa8aa8888aa8aa8aabbd
    dbb888aa8aa8aa8aa8aa8a8aa8a8aa8aa8aa8aa8aa888bbd
    dccaa8aa8888aa8aa8aa8a8aa8a8aa8aa8aa8888aa8aaccd
    bcbaa8aa8aa8aa8aa8aa888aa888aa8aa8aa8aa8aa8aabcb
    dbbaa8888aa8aa8aa888ccbbbbcc888aa8aa8aa8888aabbd
    dbbaa8aa8aa8aa888ccbbbbbbbbbbcc888aa8aa8aa8aabbd
    dcc888aa8aa888ccbbbbbccccccbbbbbcc888aa8aa888ccd
    bcbaa8aa888ccbbbbbccbddddddbccbbbbbcc888aa8aabcb
    dbbaa8aaccbbbbbccbddddddddddddbccbbbbbccaa8aabbd
    dbbaaccbbbbcccbddddddddddddddddddbcccbbbbccaabbd
    dcccbbbbcccbdddbccbbbbbbbbbbbbccbdddbcccbbbbcccd
    ccccccccbbbbbbbcbddddddddddddddbcbbbbbbbcccccccc
    bddddddddddddbcddddddddddddddddddcbddddddddddddb
    bbcbdddddddddcbd1111111111111111dbcdddddddddbcbb
    bbbcccccccccccd1bbbbbbbbbbbbbbbb1dcccccccccccbbb
    bbbbdddddddddc11beeeeeeeeeeeeeeb11cdddddddddbbbb
    bbb8aaaaaaa8dc1be3b33b33b33b33beb1cd8aaaaaaa8bbb
    bbb888888888dc1be3b33b33b33b33beb1cd888888888bbb
    bbb833333338dcbbf3b3effffffe33bebbcd833333338bbb
    bbb83ff3ff38dcbbf3bffffffffff3bebbcd83ff3ff38bbb
    bbb83cc3cc38dcbbf3effffffffffebebbcd83cc3cc38bbb
    bbb833333338dcbbf3eeeeeeeeeeeebebbcd833333338bbb
    cbb83ff3ff38dcbbe3b33b33b33b33bebbcd83ff3ff38bbc
    cbb83cc3cc38dcbbe3b33b33b33b33bebbcd83cc3cc38bbc
    ccbbbbbbbbbbdcbbe3b33b33b33feeeebbcdbbbbbbbbbbcc
    .cbbdddddddddcbbe3b33b33b33ffffebbcdddddddddbbc.
    ..cbdbbbdbbbdcbbf3b33b33b33f33febbcdbbbdbbbdbc..
    ...cdbbbdbbbdcbbf3b33b33b33bffeebbcdbbbdbbbdc...
    ....bddddddddcbbf3b33b33b33b33bebbcddddddddb....
    .....bdbbbdddcbbf3b33b33b33b33bebbcdddbbbdb.....
    ......bcccbbbcbbe3b33b33b33b33bebbcbbbcccb......
    `, SpriteKind.Food)
tiles.placeOnTile(mySprite, tiles.getTileLocation(15, 16))
let minRobot = sprites.create(img`
    ........................
    ...........bb...........
    ..........bbbb..........
    ........bbbbbbbb........
    .......bbbbbbbbbb.......
    .......bf2f33f2fb.......
    .......bbbb33bbbb.......
    ........babaabab........
    .........ab33ba.........
    ........babaabab........
    .....cbbbbbbbbbbbbc.....
    ....cbcbaaaaaaaabcbc....
    ...bbcbca666666acbcbb...
    ..b2bbc..a5555a..cbb2b..
    .5422b....a66a....b2245.
    .544b....bbaabb....b445.
    5555....bbb..bbb....5555
    55......ccc..ccc......55
    ........bbb..bbb........
    ........ccc..ccc........
    ........bbb..bbb........
    .......5424554245.......
    ........545..545........
    .........5....5.........
    `, SpriteKind.Player)
tiles.placeOnTile(minRobot, mySprite.tilemapLocation())
controller.moveSprite(minRobot)
scene.cameraFollowSprite(minRobot)
// @highlight
let krabbeAntall = 0
```

### Steg 20 Angrepsbølger 4
Nå kan du starte på endringene som trengs i ``||loops:forever||``-løkken.
Først må du hente den lille ovale ``||variables:krabbeAntall||``-blokken fra ``||variables:Variables||``-menyen og dra den inn der det står 0 øverst i ``||loops:repeat 0 times||``-blokken.
Klikk på lyspæren for å se hvordan det skal se ut. Klikk ``||scene:Next||`` for å gå videre.

```blocks
let krabbeAntall = 0
forever(function () {
    // @highlight
    for (let index = 0; index < krabbeAntall; index++) {
        krabbeRobot = sprites.create(img`
            . . . . . . 1 . . 1 . . . . . . 
            . . . . . 1 f 1 1 f 1 . . . . . 
            . . 2 2 . . 1 . . 1 . . 2 2 . . 
            . 2 . . 2 . 2 . . 2 . 2 . . 2 . 
            2 . 2 . . 2 2 2 2 2 2 . . 2 . 2 
            . 2 . 2 2 2 2 2 2 2 2 2 2 . 2 . 
            2 . . 2 2 2 2 2 2 2 2 2 2 . . 2 
            . . 2 . 2 2 2 2 2 2 2 2 . 2 . . 
            . 2 . 2 . 2 2 2 2 2 2 . 2 . 2 . 
            2 . . . 2 . . . . . . 2 . . . 2 
            . . 2 2 2 2 . . . . 2 2 2 2 . . 
            . . 2 2 2 . . . . . . 2 2 2 . . 
            . . . 2 2 2 2 . . 2 2 2 2 . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            `, SpriteKind.Enemy)
        tiles.placeOnRandomTile(krabbeRobot, assets.tile`transparency16`)
        krabbeRobot.follow(minRobot)
    }
})
```

### Steg 21 Angrepsbølger 5
Foreløpig er variabelen ``||variables:krabbeAntall||`` satt til 0, derfor kommer det ingen krabber.
Før du gjør noe med det, må du sette inn pausen som bestemmer hvor lang tid det går mellom angrepene.
Hent en ``||loops:pause 100 ms||``-blokk fra ``||loops:Lopps||``-menyen og sett den inn i ``||loops:forever||``-blokken under resten av koden.
Endre 100 til 5000. Da går det 5 sekunder mellom hvert krabbeangrep.
Klikk ``||scene:Next||`` når du har gjort det.

```blocks
forever(function () {
    for (let index = 0; index < krabbeAntall; index++) {
        krabbeRobot = sprites.create(img`
            . . . . . . 1 . . 1 . . . . . . 
            . . . . . 1 f 1 1 f 1 . . . . . 
            . . 2 2 . . 1 . . 1 . . 2 2 . . 
            . 2 . . 2 . 2 . . 2 . 2 . . 2 . 
            2 . 2 . . 2 2 2 2 2 2 . . 2 . 2 
            . 2 . 2 2 2 2 2 2 2 2 2 2 . 2 . 
            2 . . 2 2 2 2 2 2 2 2 2 2 . . 2 
            . . 2 . 2 2 2 2 2 2 2 2 . 2 . . 
            . 2 . 2 . 2 2 2 2 2 2 . 2 . 2 . 
            2 . . . 2 . . . . . . 2 . . . 2 
            . . 2 2 2 2 . . . . 2 2 2 2 . . 
            . . 2 2 2 . . . . . . 2 2 2 . . 
            . . . 2 2 2 2 . . 2 2 2 2 . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            `, SpriteKind.Enemy)
        tiles.placeOnRandomTile(krabbeRobot, assets.tile`transparency16`)
        krabbeRobot.follow(minRobot)
    }
// @highlight
pause(5000)   
})
```

### Steg 22 Angrepsbølger 6
Nå mangler bare en liten ting, så har du et spill med angrepsbølger!
Hent blokken ``||variables:change krabbeAntall by 1||`` fra ``||variables:Variables||``-menyen og plasser den nederst i ``||loops:forever||``-blokken, under resten av koden din.
Når spillet starter, har du nå 5 sekunder på deg før første krabberobot angriper.
Etter 5 sekunder vil en krabberobot dukke opp fra havet et sted, og begynne å jage deg.
Etter 10 sekunder kommer det to til. Etter 15 sekunder kommer det tre til, osv.
Hvor lenge klarer du å holde dem unna?

```blocks
forever(function () {
    for (let index = 0; index < krabbeAntall; index++) {
        krabbeRobot = sprites.create(img`
            . . . . . . 1 . . 1 . . . . . . 
            . . . . . 1 f 1 1 f 1 . . . . . 
            . . 2 2 . . 1 . . 1 . . 2 2 . . 
            . 2 . . 2 . 2 . . 2 . 2 . . 2 . 
            2 . 2 . . 2 2 2 2 2 2 . . 2 . 2 
            . 2 . 2 2 2 2 2 2 2 2 2 2 . 2 . 
            2 . . 2 2 2 2 2 2 2 2 2 2 . . 2 
            . . 2 . 2 2 2 2 2 2 2 2 . 2 . . 
            . 2 . 2 . 2 2 2 2 2 2 . 2 . 2 . 
            2 . . . 2 . . . . . . 2 . . . 2 
            . . 2 2 2 2 . . . . 2 2 2 2 . . 
            . . 2 2 2 . . . . . . 2 2 2 . . 
            . . . 2 2 2 2 . . 2 2 2 2 . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            `, SpriteKind.Enemy)
        tiles.placeOnRandomTile(krabbeRobot, assets.tile`transparency16`)
        krabbeRobot.follow(minRobot)
    }
    pause(5000)
    // @highlight
    krabbeAntall += 1
})
```

### Steg 23 Spill på tid
En annen måte å gjøre spillet vanskeligere på, er å begrense tiden du har til å samle poeng.
Du kan sette inn en nedtelling i slutten av ``||loops:on start||``-blokken. Nedtellingsblokken finner du i ``||info:Info||``-menyen.
Hent en ``||info:start countdown 10 s||`` og sett den inn nederst i ``||loops:on start||``-blokken.
Du kan velge hvor mange sekunder du har til rådighet ved å endre tallet 10 til noe annet.
Klikk ``||scene:Next||`` når du har testet spillet og er fornøyd med valg av tid. Hvor mange poeng klarer du på 30 sekunder?

```blocks
let krabbeRobot: Sprite = null
info.setLife(6)
scene.setBackgroundColor(9)
tiles.setTilemap(tilemap`level1`)
let mySprite = sprites.create(img`
    ....................8a8aa8a8....................
    .................aaa888aa8a8aaa.................
    ..............aaa8aa8a8aa888aa8aaa..............
    ...........8aa8aa8888a8aa8a8888aa8aa8...........
    ........8888aa8aa8aa8a8aa8a8aa8aa8aa8888........
    .....aaa8aa8aa8888aa8a8aa8a8aa8888aa8aa8aaa.....
    ...aa8888aa8aa8aa8aa888aa888aa8aa8aa8aa8888aa...
    dccaa8aa8aa8888aa8aa8a8aa8a8aa8aa8888aa8aa8aaccd
    bcb888aa8aa8aa8aa8aa8a8aa8a8aa8aa8aa8aa8aa888bcb
    dbbaa8aa8888aa8aa8888a8aa8a8888aa8aa8888aa8aabbd
    dbbaa8aa8aa8aa8888aa8a8aa8a8aa8888aa8aa8aa8aabbd
    dccaa8888aa8aa8aa8aa888aa888aa8aa8aa8aa8888aaccd
    bcbaa8aa8aa8888aa8aa8a8aa8a8aa8aa8888aa8aa8aabcb
    dbb888aa8aa8aa8aa8aa8a8aa8a8aa8aa8aa8aa8aa888bbd
    dbbaa8aa8888aa8aa8aa8a8aa8a8aa8aa8aa8888aa8aabbd
    dccaa8aa8aa8aa8aa8888a8aa8a8888aa8aa8aa8aa8aaccd
    bcbaa8888aa8aa8888aa888aa888aa8888aa8aa8888aabcb
    dbbaa8aa8aa8888aa8aa8a8aa8a8aa8aa8888aa8aa8aabbd
    dbb888aa8aa8aa8aa8aa8a8aa8a8aa8aa8aa8aa8aa888bbd
    dccaa8aa8888aa8aa8aa8a8aa8a8aa8aa8aa8888aa8aaccd
    bcbaa8aa8aa8aa8aa8aa888aa888aa8aa8aa8aa8aa8aabcb
    dbbaa8888aa8aa8aa888ccbbbbcc888aa8aa8aa8888aabbd
    dbbaa8aa8aa8aa888ccbbbbbbbbbbcc888aa8aa8aa8aabbd
    dcc888aa8aa888ccbbbbbccccccbbbbbcc888aa8aa888ccd
    bcbaa8aa888ccbbbbbccbddddddbccbbbbbcc888aa8aabcb
    dbbaa8aaccbbbbbccbddddddddddddbccbbbbbccaa8aabbd
    dbbaaccbbbbcccbddddddddddddddddddbcccbbbbccaabbd
    dcccbbbbcccbdddbccbbbbbbbbbbbbccbdddbcccbbbbcccd
    ccccccccbbbbbbbcbddddddddddddddbcbbbbbbbcccccccc
    bddddddddddddbcddddddddddddddddddcbddddddddddddb
    bbcbdddddddddcbd1111111111111111dbcdddddddddbcbb
    bbbcccccccccccd1bbbbbbbbbbbbbbbb1dcccccccccccbbb
    bbbbdddddddddc11beeeeeeeeeeeeeeb11cdddddddddbbbb
    bbb8aaaaaaa8dc1be3b33b33b33b33beb1cd8aaaaaaa8bbb
    bbb888888888dc1be3b33b33b33b33beb1cd888888888bbb
    bbb833333338dcbbf3b3effffffe33bebbcd833333338bbb
    bbb83ff3ff38dcbbf3bffffffffff3bebbcd83ff3ff38bbb
    bbb83cc3cc38dcbbf3effffffffffebebbcd83cc3cc38bbb
    bbb833333338dcbbf3eeeeeeeeeeeebebbcd833333338bbb
    cbb83ff3ff38dcbbe3b33b33b33b33bebbcd83ff3ff38bbc
    cbb83cc3cc38dcbbe3b33b33b33b33bebbcd83cc3cc38bbc
    ccbbbbbbbbbbdcbbe3b33b33b33feeeebbcdbbbbbbbbbbcc
    .cbbdddddddddcbbe3b33b33b33ffffebbcdddddddddbbc.
    ..cbdbbbdbbbdcbbf3b33b33b33f33febbcdbbbdbbbdbc..
    ...cdbbbdbbbdcbbf3b33b33b33bffeebbcdbbbdbbbdc...
    ....bddddddddcbbf3b33b33b33b33bebbcddddddddb....
    .....bdbbbdddcbbf3b33b33b33b33bebbcdddbbbdb.....
    ......bcccbbbcbbe3b33b33b33b33bebbcbbbcccb......
    `, SpriteKind.Food)
tiles.placeOnTile(mySprite, tiles.getTileLocation(15, 16))
let minRobot = sprites.create(img`
    ........................
    ...........bb...........
    ..........bbbb..........
    ........bbbbbbbb........
    .......bbbbbbbbbb.......
    .......bf2f33f2fb.......
    .......bbbb33bbbb.......
    ........babaabab........
    .........ab33ba.........
    ........babaabab........
    .....cbbbbbbbbbbbbc.....
    ....cbcbaaaaaaaabcbc....
    ...bbcbca666666acbcbb...
    ..b2bbc..a5555a..cbb2b..
    .5422b....a66a....b2245.
    .544b....bbaabb....b445.
    5555....bbb..bbb....5555
    55......ccc..ccc......55
    ........bbb..bbb........
    ........ccc..ccc........
    ........bbb..bbb........
    .......5424554245.......
    ........545..545........
    .........5....5.........
    `, SpriteKind.Player)
tiles.placeOnTile(minRobot, mySprite.tilemapLocation())
controller.moveSprite(minRobot)
scene.cameraFollowSprite(minRobot)
let krabbeAntall = 0
info.startCountdown(30)
forever(function () {
    for (let index = 0; index < krabbeAntall; index++) {
        krabbeRobot = sprites.create(img`
            . . . . . . 1 . . 1 . . . . . . 
            . . . . . 1 f 1 1 f 1 . . . . . 
            . . 2 2 . . 1 . . 1 . . 2 2 . . 
            . 2 . . 2 . 2 . . 2 . 2 . . 2 . 
            2 . 2 . . 2 2 2 2 2 2 . . 2 . 2 
            . 2 . 2 2 2 2 2 2 2 2 2 2 . 2 . 
            2 . . 2 2 2 2 2 2 2 2 2 2 . . 2 
            . . 2 . 2 2 2 2 2 2 2 2 . 2 . . 
            . 2 . 2 . 2 2 2 2 2 2 . 2 . 2 . 
            2 . . . 2 . . . . . . 2 . . . 2 
            . . 2 2 2 2 . . . . 2 2 2 2 . . 
            . . 2 2 2 . . . . . . 2 2 2 . . 
            . . . 2 2 2 2 . . 2 2 2 2 . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            . . . . . . . . . . . . . . . . 
            `, SpriteKind.Enemy)
        tiles.placeOnRandomTile(krabbeRobot, assets.tile`transparency16`)
        krabbeRobot.follow(minRobot)
    }
    pause(5000)
    krabbeAntall += 1
})
```

### Steg 24 Gratulerer med ferdig spill!

Da er spillet ferdig! Eller er det det? 
Kanksje du har lyst til å utvide spillet ditt med lyder og animasjoner? Eller kanskje du har lyst til å gjøre andre endringer?
Mulighetene er nesten uendelige, og det kan være vanskelig å bestemme seg for hva man vil gjøre videre.
Når du trykker på ``||scene:Done||`` vil det dukke opp et vindu som lar deg dele spillet ditt.
Det kan du enten krysse ut, eller du kan gi spillet et navn og publisere det, slik at andre kan teste det.
Når vinduet forsvinner, kommer du tilbake til spillet ditt, men nå har du tilgang på alle blokkene i MakeCode Arcade.
Inne på MakeCode Arcade finnes det også flere tutorialer som denne for mange typer spill, men de fleste er på engelsk.
Om du klikker der det står ``||controller:MakCode Arcade||`` oppe i høyre hjørne av dette vinduet, kommer du ut i hovedmenyen.
Der finner du mange aktiviteter om du har lyst til å lære mer om koding.
Klikk på ``||scene:Done||`` for å avslutte tutorialen.

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
