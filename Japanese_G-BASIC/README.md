# Japanese G-BASIC Statements <br> (日本語G-BASICのステートメント)

Work in progress (1/Mar/2026).<br>

## ANIME アニメ
This is the command for manipulating hardware sprites via the TMS9918A VDP.  There can be up to 32 sprites with a limit of four per horizontal scan line (to avoid flicker).<br>

```アニメ <sprite number> = イチ(y,x)```
Display the specified sprite at coordinates (x,y).<br>
The X coordinate is 1-256 and Y coordinate is 1-192.<br>
Set the Y coordinate to 193 to hide the sprite.<br>
Uses the ICHI function to set the first location.<br>

```アニメ <sprite 1> = アニメ <sprite 2>```
Copy sprite 1 to sprite 2's location.

## CELL セル
- セル (seru)

The screen is divided into a grid of 8x8 pixel cells, giving a 32x24 cell layout, numbered from 1 (top left) to 768 (bottom right).  The セル command lets programs manipulate these cells as building blocks for backgrounds, maps or simple animations.<br>

```セル(from cell number) = セル(to cell number)```
Copy graphics from cell to cell.<br>

```<variable> = セル(cell number)```
Read the cell bit pattern into the variable.<br>
It returns a 16-bit value which represents the top two lines (16 pixels) of the cell's bitmap.  The foreground bits are set to 1.<br>
This is useful for collision detection, reading map data or checking what is at a position.<br>

```セル(cell number) = <variable>```
Writes a 16-bit value to draw on the top two lines of the specified cell.<br>

## FOR/TO/STEP/NEXT マワレ/カラ/カンカク/トジル
- マワレ = 回れ (maware), loop/go around
- カラ = から (kara), from
- カンカク = 間隔 (kantaku), interval
- トジル = 閉じる (tojiru), close/end

This is a little bit weird (in my head):<br>
```
マワレ <line number of NEXT> <variable name> = <initial value> カラ <end value> カンカク <step value>
<statements to loop>
トジル
```
Restating:<br>
- ```マワレ <line number of NEXT>``` = line number where the トジル is, we will loop all lines between
- ```<variable name> = <initial value> カラ <end value>``` = from initial value to end value
- ```カンカク <step value>``` = increment step of variable
- ```トジル``` = NEXT

An example:<br>
```
10 マワレ 30 I = 1 カラ 10 カンカク 2
20 カケ　"Looping"
30 トジル
```

## GETX ヨコ
- ヨコ = 横 (yoko), horizontal

```<variable name> = ヨコ(sprite number)```

Get the current X coordinate (1-256) of the specified sprite.<br>

## GETY タテ
- タテ = 縦 (tate), vertical

```<variable name> = タテ(sprite number)```

Get the current Y coordinate (1-192, 193 is off-screen) of the specified sprite.<br>

## GOTO ニイケ
- ニイケ = に行け (ni ike), go to<br>

```<line number> ニイケ```<br>

## ICHI イチ
- イチ = 一 (ichi), one<br>

Used in the ANIME command to set the first location for the sprite.<br> 

## IF/THEN/GOTO モシ/ナラバ/ニイケ
- モシ = もし (moshi), if
- ナラバ = ならば (naraba), then
- ニイケ = に行け (ni ike), go to<br>

```モシ <condition> ナラバ <line number> ニイケ```<br>

If \<condition\> is met then we will jump to \<line number\>.<br>
Comparisons between anime are determined by the top-left co-ordinate.<br>
The timer will reset when the condition is met.<br>

## KEY キイ
- キイ (kii), key<br>

```キイ <controller> <variable 1>,<variable 2>```<br>

Get the state of the controller 1 or controller 2.<br>
The variables will hold the status:
| Variable 1 (direction) | Variable 2 (fire) |
|------------------------|-------------------|
| 0 = not pressed        | 0 = not pressed   |
| 1 = up                 | 1 = SL button     |
| 2 = up & right         | 2 = SR button     |
| 3 = right              ||
| 4 = down & right       ||
| 5 = down               ||
| 6 = down & left        ||
| 7 = left               ||
| 8 = up & left          ||


## LET シキ
- シキ = 式 (shiki), formula/expression/equation<br>

```シキ <variable name> = <value>```<br>

## PRINT カケ
- カケ = 書け (kake), write

```
カケ <cell number>,"<string>"
カケ <cell number>,<variable name>
カケ <cell number>,+<variable name>
```

## RND ランスウ
- ランスウ = 乱数 (ransū), random number

```<variable name> = ランスウ(limit)```
Assign a random number between 0 and \<limit\> to the variable.<br>

## SOUND オト
- オト = 音 (oto), sound

```
オト <sound type>
オト イチオン
オト ニオン
オト サンオン
オト シオン
```

- イチオン (ichion, 1st) = short high beep for keypress/click
- ニオン (nion, 2nd) = low buzz for error or invalid action/error
- サンオン (sanon, 3rd) = ding for menu select or decision/success
- シオン (shion, 4th) = explosion for hit/crash/effect
