# Japanese G-BASIC Statements <br> (日本語G-BASICのステートメント)

Work in progress (1/Mar/2026).<br>

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

## GOTO ニイケ
- ニイケ = に行け (ni ike), go to<br>

```<line number> ニイケ```<br>

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
