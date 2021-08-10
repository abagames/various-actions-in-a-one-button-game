# How to realize various actions in a one-button game

## Introduction

Recently, I've been making a lot of mini-games using my own game library [crisp-game-lib](https://github.com/abagames/crisp-game-lib). Many of [those games](http://www.asahi-net.or.jp/~cs8k-cyu/browser.html) are one-button games. The one-button games discussed in this article are not games that use one button in addition to the joystick for movement, but games that use only one button purely for control.

The advantage of one-button games is that they are easy to understand and operate, even on touch devices. There is almost no need to explain the operations in the game, because the player can see all the possible actions that can occur in the game by pressing a button. Also, when playing with a touch device, you can control the game by tapping or holding anywhere on the screen, so you don't have to deal with the problem that often occurs with virtual pads where you don't feel the buttons being pressed.

One obvious drawback of one-button games is that it is difficult to give variation to the actions in the game. Even the left-right movement, which can be easily achieved with a joystick, requires a special control that reverses the direction of movement when the button is pressed. 

Therefore, the problem in creating a one-button game is how to give variation to the interaction to the game with just one button. I would like to discuss how to solve the above problem using some examples of one-button games that I have made.

## Introduce special movements

In one-button games, the following actions are commonly performed by the player in the game screen when a button is pressed.

- Reverse the direction of movement / Turn 90 degrees
- Jump / Flap wings
- Shoot the bullet

The following game is an example of a game where the direction of movement is reversed by a button (Click on the screenshot to play it in your browser).

[![THUNDER](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/thunder/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?thunder)

If a game requires the player only to move in two directions, it is possible to make it a one-button game by devising obstacles and bonus items in the game. However, it is not really a game that has the unique characteristics as a one-button game.

If the actions that occur with the button operation are rarely seen in regular games, players will be strongly impressed by the fact that the game is unique to one-button operation. Some examples of such special behavior are listed below.

### Teleportation

[![CYWALL](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/cywall/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?cywall)

A point where the player can move is drawn on the screen, and the player instantly moves to the nearest point at the moment of pressing. The advantage of this behavior is that the player can move at a fast pace by pressing a button.

### Splitting

[![DIVARR](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/divarr/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?divarr)

Each time you press a button, the missile splits. You can enjoy the increased attack power just by pushing the button rapidly. But that's not enough to make it a game, you need to make objects appear that you can't shoot.

### Choice

[![NOT TURN](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/notturn/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?notturn)

[![JUMP ON](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/jumpon/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?jumpon)

At a certain point, the player can choose to turn, jump to the floor, etc. It should be clear to the player that there is a place in the game screen where they can choose which way to go.

### Reversing attribute

[![NS CLIMB](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/nsclimb/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?nsclimb)

Each time you press a button, the attributes, such as N and S poles, are switched. The key of the game is to think about what to use for the attributes and how the attributes relate to other objects in the game.

### Other special actions

[![LADDER DROP](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/ladderdrop/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?ladderdrop)

Drop the floor and ladders that are moving left and right with good timing. It is also a one-button game version of the falling block game.

[![NUMBER LINE](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/numberline/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?numberline)

Sum the numbers that are flowing. This is too specific to be used as a reference for creating other games, but it is an example of the many possible actions that can be assigned to a button.

## Use of button press-and-hold operation

In a one-button game, some action usually occurs the moment you press a button, but you can also make something happen continuously while you hold it down.

### Adjust angle and distance

[![NUMBER BALL](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/numberball/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?numberball)

As is common in golf games, the angle of the shot increases gradually as you hold down the button, so you have to release the button at just the right moment to launch the ball. This game is differentiated from golf games by the mysterious rule that if the number you hit matches the number on the floor, the floor disappears.

[![FROOOOG](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/froooog/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?froooog)

The distance the frog jumps is determined by the time the button is held down.

### Telescoping

[![PIN CLIMB](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/pinclimb/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?pinclimb)

While you hold down the button, the stick stretches, and when you release it, it shrinks. The extending and retracting motion is often used in combination with the terrain in the game screen, such as when the extended stick gets caught in the terrain and moves forward by extending further from there.

[![SQUARE BAR](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/squarebar/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?squarebar)

When combined with geometric figures, complex movements can be realized using only stretching and shrinking motions.

[![TAPE J](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/tapej/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?tapej)

Stretching your body increases your points, but it also increases the risk of the stretched part hitting an obstacle. This will balance the risk-reward in the game.

### Defend against / Prevent being hit

[![EMBATTLED](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/embattled/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?embattled)

As long as you hold down the button, you will not be hit by shells. When the tanks get close enough, you can release your defenses and avoid shells by moving up and down, and the tanks will fight each other on their own.

[![REFLECTOR](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/reflector/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?reflector)

A defensive wall that reflects enemy bullets is always attached below the player, but as long as the button is held down, the defensive wall becomes smaller instead of allowing a powerful counterattack.

[![BAMBOO](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/bamboo/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?bamboo)

When you hold the button down, you will not hit the bamboo and can slip through the back of the bamboo. Then you will be able to get in between the bamboos and bounce around, allowing you to quickly cut the bamboo.

### Other special actions

[![CHARGE BEAM](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/chargebeam/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?chargebeam)

Charge energy. The game is not viable unless you make it meaningful to adjust the amount of charge.

[![LASER FORTRESS](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/laserfortress/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?laserfortress)

Cleave. A super-powerful subclass of shooting. By mixing allies with enemies, the super-powerful attack is adjusted to be a drawback as well.

[![SHINY](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/shiny/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?shiny)

It rains and it clears. While it is raining, people will move faster, and you can make them move to the far right earlier. This is so unusual that it is difficult to adapt it to other games.

## Combination of multiple actions

Combining the above actions is also a standard way to create a one-button game.

[![SCRAMBIRD](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/scrambird/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?scrambird)

Flap wings + shoot,

[![TILTED](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/tilted/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?tilted)

multiple jump + reverse the direction and

[![UP SHOT](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/upshot/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?upshot)

shoot + stop.

Another combination approach is to have a certain behavior have multiple effects in the game.

[![BOMB UP](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/bombup/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?bombup)

In this game, you can use the button to drop and explode bombs, but in addition to that, the blast will affect the player by blowing it up. By adjusting the position of the explosion, the player's movement can be controlled. This makes it possible to perform quite complex actions with a single button, but if you overdo it, it becomes too difficult to control the player's movements, so it is important to adjust the level of complexity.

## Combination with rotational motion

Similar to angle adjustment, there is also a way to make the game more timing-oriented, where the player or barrel is always spinning and jumping out or shooting at the right moment.

[![ORBIT MAN](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/orbitman/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?orbitman)

The player's jumping direction is rotated so that the player jumps out at the right time in the direction of the next star.

[![ARCFIRE](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/arcfire/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?arcfire)

The barrel of the gun is rotating, so shoot at the right time when the barrel is facing the enemy. In this game, you can adjust the range and attack area by holding down the button, and move forward a little in that direction as soon as you fire. In this way, various actions can be performed with a single button.

## Use of terrain

If it's difficult to add variation to the movements using only button inputs, you can make the movements change depending on the terrain the player is standing on.

[![TURBULENT](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/turbulent/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?turbulent)

Even for the action of jumping with a button, by making the terrain a rough sea surface, you can change the direction of the jump depending on the timing.

[![SUB JUMP](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/subjump/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?subjump)

By setting the lower half of the screen as underwater and the upper half as air, the button can play multiple roles, such as ascending when in the water and jumping when in the air.

## Use of items

In addition to terrain, items can be used for variations in behavior. By making the rules to change the player's mode when an item is taken, the choice of taking or not taking an item can be used instead of an input.

[![MIRROR FLOOR](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/mirrorfloor/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?mirrorfloor)

Each time you take a coin, the direction of gravity switches. If you don't look carefully at the position of the next floor and choose whether or not to take the coin, you will not be able to jump to the next floor.

[![LIFT UP](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/liftup/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?liftup)

When you take an item, your direction of movement changes. You need to get the reversing items before you hit the spikes on the left and right.

[![REBIRTH](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/rebirth/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?rebirth)

You are run over by a truck and move to the opposite world. Whether the truck is an item is debatable, but you can choose to be run over by the truck or not by looking at the location of the next diamond.

[![R WHEEL](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/rwheel/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?rwheel)

When you pick up an item, it fires a yellow laser downward to destroy the obstacle spikes. The game also has several other things that happen in response to the action of jumping when you press the button: fires a purple laser downward that makes spikes grow, spikes turn around and come back to the player, and items appear when you jump.

## Conclusion

As you can see, it is possible to create many variations of movements even with a single button. Even with just the games listed in this article, we found that it is possible to create quite a variety of game types.

The advantage of one-button games is that they are easy to control, but this can lead to unexpected traps. The trap is that you can sometimes create a game where you can score infinite points just by hitting the button repeatedly or holding it down. Therefore, after making a game, be sure to play it by hitting and holding the button. Even if you don't intend to do so, you should be aware that such a game can be created.

Also, as a basic premise, there is no relationship between the fact that a game is a one-button game and whether it is interesting or boring. Therefore, it is important that the game has a sense of exhilaration and tension, and a good balance of risk and reward, and should be interesting as a game. After that, it is necessary to consider whether the game can be made into a one-button game.
