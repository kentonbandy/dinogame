# Dino Game
A TEC Redshift game written using the Exapunks coding language (click to watch the short demo video)

[![Dino Game Demo Video](docs\screenshot.png)](https://www.youtube.com/watch?v=_VK4LMyH1V8)

---
## What in the world is going on?

Hi! This is a recreation of the [Chrome Dinosaur T-Rex Game](https://trex-runner.com/) made for a fictional handheld console called the TEC Redshift in the game [Exapunks!](https://www.zachtronics.com/exapunks/)

Exapunks is a puzzle game featuring an assembly coding language that controls microscopic virus-shaped robots called EXAs. At one point in the game the TEC Redshift is unlocked, and players can freely create games by programming EXAs to interface with the console.

The Redshift features four registers for the D pad and buttons and four registers for audio output. Each EXA can store a 10x10 sprite that can be pre-loaded or altered one pixel at a time through code. To sync at 30 frames per second (the Redshift's refresh rate), the WAIT command is used to pause execution of an EXA's code until the next screen refresh.

Limited instructions for creating games for the Redshift are given in page 7-11 of the [2nd issue of "Trash World News"](https://exazines.mattmerr.com/zine02.html), a fictional publication that provides instructions for the game.

## How to play

This game can be played in [Exapunks](https://store.steampowered.com/app/716490/EXAPUNKS/) or the [free TEC Redshift player](https://store.steampowered.com/app/948420/EXAPUNKS_TEC_Redshift_Player/). With the solution browser open in game, drag and drop the DINO GAME.png image into the browser.

OR, with a little more setup, you can play this and other TEC Redshift games on any device that runs Retroarch! My friend [Travis](https://github.com/thieman) made an [emulator for the TEC Redshift](https://github.com/thieman/exa-rs) in rust which is totally insane and awesome. This game is featured in the demo video for the emulator :D

To play using a keyboard, the enter key starts the game, and the W and S keys jump and crouch.

## Fun Facts

The Dino is actually six sprites (four while standing, two more when crouching).

The ground is ten sprites continuously being created offscreen to the right, moved incrementally to the left, and deleted offscreen on the left. Each dirt sprite is generated using RNG to choose whether it is flat, a hill, or a valley, and the dirt spots are also randomly placed.

There are 10 permutations of "enemies" that spawn within a range of distance to one another, generated at random.

After macro commands are expanded (when the program runs) there are over 2900 lines of code (they're short lines though).

While the Redshift does have a built in font library, I had to create a font for numbers in order to draw the score in a smaller size. Here's the font, feel free to use it in your own Redshift games :)


```
NOTE NUMBER COORDS WILL
NOTE DRAW ON TOP LEFT
NOTE OF SPRITE

NOTE 0
DATA 0
DATA 10 20 11 31 12 32
DATA 13 33 14 24 34 0

NOTE 1
DATA 20 11 21 22 23 24 0

NOTE 2
DATA 10 20 31 22 13 14
DATA 24 34 0

NOTE 3
DATA 10 20 31 22 33 14
DATA 24 0

NOTE 4
DATA 10 11 31 12 22 32
DATA 33 34 0

NOTE 5
DATA 10 20 30 11 12 22
DATA 33 14 24 0

NOTE 6
DATA 20 30 11 12 22 13
DATA 33 14 24 34 0

NOTE 7
DATA 10 20 30 31 32 33
DATA 34 0

NOTE 8
DATA 10 20 11 31 12 22
DATA 32 13 33 14 24 34 0

NOTE 9
DATA 10 20 11 31 12 22
DATA 32 33 34 0
```