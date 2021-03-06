Authors:	Andrew Bender
			Thomas Nagl
Date:		February 2010

This is a simple game that uses the Processing JS framework to demonstrate a variety of interactive flocking rules.

NB: USE FIREFOX!  There seems to be a problem with the webkit (ie Chrome & Safari) javascript engine rendering fonts in the canvas.  The game relies on some fonts.  Firefox displays them correctly, but Chrome and Safari do not.


Flocking Behaviors:
Prey
-Separation from other Prey and Protectors to stop collisions.
-Alignment & Cohesion with other Prey and Protectors to try and move in a group.
-Fleeing from predators to avoid being eaten.

Protectors
-Separation from other Protectors and Prey to stop collisions.
-Alignment & Cohesion with other Protectors and Prey to try and move in a group.
-Chasing predators to try and destroy them.

Predators
-When the mouse is in the upper left-hand corner the Predator follows these flocking rules:
---Separation from other Predators to stop collisions.
---Alignment & Cohesion with other Predators to try and move in a group.
---Chasing Prey to try and eat them.
---Fleeing from Protectors to avoid being destroyed.
---If the Predator is moving too fast, the stamina bar decreases.
---If the Predator is moving slow enough, the stamina bar increases.
---If the stamina bar reaches 0, the Predator is locked into a very slow speed until stamina reaches 50.
-When the mouse is being used, the Predator follows these rules:
---Moves toward the mouse's location
---Separation from other Predators to stop collisions.
---The farther away the mouse (past 100 pixels) the faster the Predator accelerates.
---The closer the mouse (within 100 pixels) the faster the Predator deccelerates.
---If the Predator is moving too fast, the stamina bar decreases.
---If the Predator is moving slow enough, the stamina bar increases.
---If the stamina bar reaches 0, the Predator is locked into a very slow speed until stamina reaches 50.

Game Aspect:
-You are the Predators(red boid) and your job is to eat the Prey(white boids) and avoid being eaten by the Protectors(blue boids).
-If you reach a killing spree(5, 10, 15, or 20 kills in a row) you recieve bonus lives.
-With each round, more Protectors are added to the game.

Performance Analysis:
-The Prey used to be the bottleneck because each Prey needed to loop through all the other Prey for each flocking rule, but this was fixed by merging the rules together and using only one iteration of each of the arraylists.
-We have the game capped at 45 frames/sec in order to keep a smooth flowing game.
-We also switched the 3D vectors that the program already had into 2D vectors.

Cool Features:
-Stamina bar
-Mouse follow
-Infinitely long game

Experimentation:
-We changed the chase and flee flocking rules to try and obtain a desired effect.
-We modified the influence of the mouse and separation rules to gain better Predator behavior.