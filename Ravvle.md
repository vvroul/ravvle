title Ravvle
author Vrouliotis Vasileios
homepage https://vvrouliotis.itch.io/

========
OBJECTS
========

Background
#0c2117

DigitalField
darkgray gray
10001
00110
10101
00010
00101

Player
#7a2816 black white
.0.0.
.0200
.0100 0101.
.0.0.

PlayerCaught
#7a2816 black white #9b7f1e
.0.0.
.0203
.0133 0101.
.0.0.

Bread
#9b7f1e #57491c
.....
.001.
.000.
.101.
.....

Baker
white brown
00000
.000.
11111
10001
.1.1.

BakerAngry
white red brown
11111
.111.
22222
20002
.2.2.

Wife
white brown
00000
.000.
11111
10001
00000

WifeAngry
white red brown
11111
.111.
22222
20002
00000

Customer
black purple red #fff9ef
.000.
31113
31113
.000.
.3.3.

CustomerNotice
black purple red #fff9ef
.222.
31113
31113
.000.
.3.3.

Boss
darkblue blue red #fff9ef
.000.
00200
00200
30203
.3.3.

BossNotice
darkblue blue red #fff9ef
.222.
00200
00200
30203
.3.3.

=======
LEGEND
=======

. = Background
P = Player
B = Bread
D = DigitalField
@ = Baker
W = Wife
C = Customer
! = Boss

=======
SOUNDS
=======

Player MOVE 97176507
Bread destroy 35977506
endlevel 83744503
startgame 19097908

================
COLLISIONLAYERS
================

Background
Bread
Player, PlayerCaught,
DigitalField
Baker, BakerAngry, Wife, WifeAngry, Customer, CustomerNotice, Boss, BossNotice

======
RULES
======

( Player eats the bread )
[Player Bread] -> [Player ]
[Player | Bread] -> [Player | ]

( Baker moves )
[down Player] [Baker] -> [down Player] [right Baker]
[up Player] [Baker] -> [up Player] [left Baker]
[left Player] [Baker] -> [left Player] [down Baker]
[right Player] [Baker] -> [right Player] [up Baker]

( Wife moves )
[down Player] [Wife] -> [down Player] [up Wife]
[up Player] [stationary Wife] -> [up Player] [down Wife]
[left Player] [Wife] -> [left Player] [right Wife]
[right Player] [Wife] -> [right Player] [left Wife]

(Customer moves)
[down Player] [stationary Customer] -> [down Player] [randomdir Customer]
[up Player] [Customer] -> [up Player] [down Customer]
[left Player] [Customer] -> [left Player] [up Customer]
[right Player] [stationary Customer] -> [right Player] [randomdir Customer]

(Boss moves)
[down Player] [stationary Boss] -> [down Player] [randomdir Boss]
[up Player] [stationary Boss] -> [up Player] [randomdir Boss]
[left Player] [stationary Boss] -> [left Player] [randomdir Boss]
[right Player] [stationary Boss] -> [right Player] [randomdir Boss]

( When there's a digital field between player and someone else, then player gets caught )
[Player no DigitalField|...|Baker] -> [PlayerCaught no DigitalField|...| < BakerAngry]
[Player no DigitalField|...|Wife] -> [PlayerCaught no DigitalField|...| < WifeAngry]
[Player no DigitalField|...|Customer] -> [PlayerCaught no DigitalField|...| < CustomerNotice]
[Player no DigitalField|...|Boss] -> [PlayerCaught no DigitalField|...| < BossNotice]

==============
WINCONDITIONS
==============

No Bread

=======
LEVELS
=======

message The sketch materialized. And it's...HUNGRY...for freshly baked bread.
message But it has to be careful and hide in the digital field in order not to be seen.

B.......
DDDD....
.DDDDD..
....DD@.
....DDB.
....DD..
P.......

message The baker's wife just arrived!

...P........
.DDD......B.
.D..DDDDDDDD
DD.........D
B....D......
.....DDDDDD.
.@DDD......D
DD..DB...W..

message We have our first customers, better stay hidden when it's possible!

d..........b.....dd
dd...dddddddd...dd.
.ddddd..d....d.dd..
..dd.b..d.c..ddddd.
..d.........ddd..dd
.d............d.c.d
pddd.ddd..d...db..d
...dddd..d.....d...
...ddb.....d..dddd.
...d.......ddd.dd..
ddddddd.wddd....d..
d..d@..d..d.b...dd.

message More customers...

..............d..d..d.....d.
....d...b.....dd............
..dddd.dddddddddd.b.d...d...
........dd......d..d....d...
..dd..d..d......dddddddddddd
..p.d....dd..d.......d...d..
....dd.ddddd..........d...d.
.....dd....dd....d.c..ddb.d.
..dd.d......dddd.......d..d.
dd.dbd......d..ddd..d..dd.d.
.ddddd..bd.ddb...d..d..d..d.
....d.....dd......d...dd..d.
.....d...dd.c..dddddddddddd.
..dddddddd.....d....dd..db..
.......ddd...d.d...dd....d.c
.w...dd..ddddddd.dd.d....d..
....dd...d.d.....d...d.@.dd.
...dd....d.d....dd...b...dd.
........dd....c.............

message Attention, today is the inspection day! The Boss is coming!

....d....b.......dd.....dd.d........
....dd..d....d...d...b..d.dd.d.b....
dd...d.d.c...dd.d.d.d.ddd.......d...
.ddd.dd.......dd......d....w.d...dd.
..d.ddddd...dddd......d.......ddd...
.d......dddd...d...!..d....ddd..ddd.
.b..@.....ddd...d.....d..ddd.....ddd
.........dd.dd...d....d.dd.....d...d
.d..d...dd...d....d..ddd..d...c.....
......ddd..d..dd..dddd...........b..
...dddd...d..dddddddddddd.....d...d.
.dd.........ddd....ddd..dddddd.....d
dd..d..dddddd....dd..dd...ddddddd.d.
..b...d.........dd....dd...dd....dd.
.....dd........dd...d..d..b.dd.d..d.
...ddd......p.dd..db...d.....d...b..
