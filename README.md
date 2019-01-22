# GN_TREK
The Star Trek game for PetitComputer (Petitcom mkII)

## Introduction

This is the Star Trek, an old well known computer game, for Petit Computer. This program is based on the Mike Mayfield's HP BASIC code.

Petit Computer is a BASIC programming environment DSiWare that works on Nintendo DSi/3DS.
A port for "Petitcom 3rd", "Smilebasic" in other regions, is availabe but I lost URL for that!

### Version 0.3
In order to avoid copyright issues, the title is "TREK" and the name of enemy is "KLILIN".

You can play with both stylus and buttons.

    +: move a cursor
    A: select
    Y: enter
    X: cancel
    L: set cursor to "WARP"
    R: set cursor to "5"
    L+R+X: quit

### Version 0.3.2
Enemies become moving around in their quadrant from Ver. 0.3.2. 

Program name is "GN_TRK03". 

### Known bugs.
Setting a large number of energy to phaser causes an overflow error.


## About the Game

See Wikipedia's entry for an overview of the game. Or read instructions in the game.

- Star Trek (text game) - Wikipedia, the free encyclopedia
-- http://en.wikipedia.org/wiki/Star_Trek_%28text_game%29

This version is based on the code written by Mike Mayfield for HP BASIC(1972). Differences to that code are followings.
- Formula for calculating phasor effect.
- The photon torpedo can destroy the star.

### Specification

#### Galaxy
- 8x8 Quadrants, 8x8 Sectors.
- There is nothing outside the galaxy.
#### Mission Period
- 30 years.
#### The initial value of the energy
- 3000 units. It is the max value. The initial value of that for enemy ship is 200.
#### Torpedos
- 10 units. It is the maximum number.
#### Enemies and Bases
- Determined by the random number. Enemy is up to three at most in a quadrant. There are at least one base in the galaxy.

### Commands

#### Warp
- Course: The directions are represented from 1 to 9 in a counter-clockwise. 1 represents the right direction.
- Factor: 8 or less. 1 unit is able to move 8 sectors. When the warp engine is broken, you can specify up to 0.2. 
Moving beyond the quadrant boundaries makes one year elapse.
#### Short Range Sensor
SRS displays the state in the sector.
#### Long Range Sensor
LRS shows the state of 9-neighbor quadrants.
The computer memorizes the result of LRS to the galaxy map.
#### Phaser
Phaser can attack multiple enemies at the same time.
Specified energy is distributed according to the number of enemies in the quadrant. Those will be multiplied by 0.5 to 1.5 randomly. Each energy is attenuated according to the distance to the enemies.
The energy efficiency for attack will be reduced when the computer is broken.
#### Torpedos
Course representation is the same to the warp direction.
You can destroy a target in one shot.
#### Shield
Shield energy for defense is allocated from available energy.
Will be destroyed when you are attacked without shields.
The shield will be shutdown while the ship is anchored to the base. The base protects the ship while it is anchored.
#### Damage Control
Display the states of the ship. A warp makes 1 unit damage repair.
Damaging or repairing occurs while warping in the probability of 20%. Value of the failure or recovery is up to 5.
#### Computer
The computer has three functions.
##### Galaxy Map
Stores the results of LRS scans.
##### Report Log
Show current status of the mission and the damaged devices.
##### Course Calculator
Show the coordinates and the distances to enemies in the quadrant.
Course calculator can calculate the direction between two points.
