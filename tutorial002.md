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
`, [myTiles.transparency16,sprites.castle.tileGrass1,sprites.castle.tilePath5], TileScale.Sixteen))
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

# Lag et spill om den store krabbekrigen
## introduksjon
### intro @unplugged

Professor K. Rabbe har laget en gigantisk hær av robotkrabber! Du må lage alt roboten din trenger for å overleve angrepene fra robotkrabbene. Steg 1: Test spillet og se om du klarer å overleve første angrepsbølge!

### Steg 1: Test spillet!

Som du ser følger krabberobotene etter roboten din, og roboten kan ikke gjøre noe for å stoppe dem. Du må lage feller som kan fange krabberobotene. Klikk på ``||scene:Next||`` under for å lære hvordan du lager en teine! 

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

### Steg 2 Legg feller med å trykke på en knapp!
Roboten din skal legge feller ved at du trykker på knapp A. Da trenger du blokken ``||controller:on A button pressed||``. Hent den fra ``||controller:Controller||``-menyen og plasser den ved siden av koden din.

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>

``` blocks
// @highlight
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
	
})
```
### Steg 3 Lag en teine-sprite
Inni blokken du la sist skal vi lage en sprite. En sprite er et lite, interaktivt bilde, akkurat som krabberobotene og roboten du kontrollerer.
Hent en ``||sprites:set mySprite2 to sprite of kind Player||``-blokk fra ``||sprites:Sprites||``-menyen. Klikk på Next når du er ferdig.

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
### Steg 4 Tegn teine-Spriten
En teine er en boks av netting til å fange fisk eller krepsdyr i. Klikk på det grå kvadratet i ``||sprites:set mySprite2 to sprite of kind Player||``-blokken og tegn en firkant eller en boks ved å bruke tegneverktøyet i sprite-editoren.
Sprite-editoren er en programsnutt som lar deg tegne og redigere sprites.
Ikke glem å trykke på ``||loops:Done||``-knappen nede i høyre hjørne av editoren når du er ferdig.
Klikk på ordet ``||variables:mySprite2||`` i ``||sprites:set mySprite2 to sprite of kind player||``-blokken og velg ``||variables:Rename variable||``. Skriv inn ``||variables:teine||`` og trykk på ``||loops:Ok||``.
Klikk på ordet ``||sprites:Player||`` i ``||sprites:set mySprite2 to sprite of kind Player||``-blokken og velg ``||sprites:Add a new kind||``. Skriv inn ``||sprites:Felle||`` og trykk på ``||loops:Ok||``.
Klikk på Next når du er fornøyd.

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
