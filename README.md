## Cube 3D (a School 42 project)

This repository contains the source code for the Cube 3D project written by a team consisting of myself and Tegerrr at 42. The code has only been tested on MacOS. 

This education project is focused on two aspects: 

- Creating a sophisticated parser, that validates a map (the part that I mainly worked on)
- Creating a Wolfenstein3D-inspired raycasting engine from scratch using only the MLX graphic library. 

##Launching Cube 3d

Clone the repository and run make in the root folder:

```bash
make
```
Then launch the executable cub3d with a path to a map file (two maps are provided) as a command line argument:

```bash
./cub3d ./maps/maze.cub
```
A window with a 3D view of the parsed map opens. Navigate around using the AWSD keys for movement and the right/left arrow keys for turning around. Press the red cross or Esc to exit. 

Now try to modify the maze.cub file: 

Change the map,  the RGB color coding of the floor and ceiling, or the paths to texture files. See if the program parses the map and whether the map passes the validation test. 

This project is for educational purposes only.

## Map parsing 

The map parser adheres to the following requirements of the 42 project description (subject): 


* The program must take as a first argument a scene description file with the .cub extension.
* The map must be composed of only 6 possible characters: 0 for an empty space, 1 for a wall, and N,S,E or W for the player’s start position and spawning orientation. 
* The map must be closed/surrounded by walls, if not the program must return an error.
* Except for the map content, each type of element can be separated by one or more empty line(s).
* Except for the map content which always has to be the last, each type of element can be set in any order in the file.
* Except for the map, each type of information from an element can be separated by one or more space(s).
* The map must be parsed as it looks in the file. Spaces are a valid part of the map must be handled. 
* You must be able to parse any kind of map, as long as it respects the rules of the map. 
* Each element’s (except the map) first information is the type identifier (composed by one or two character(s)), followed by all specific pieces of information for each object in a strict order such as : 
* North texture: NO ./path_to_the_north_texture
  - identifier: NO
  - path to the north texure 
* South texture: SO ./path_to_the_south_texture
  - identifier: SO
  - path to the south texure 
* West texture: WE ./path_to_the_west_texture
  - identifier: WE
  - path to the west texure 
* East texture: EA ./path_to_the_east_texture
  - identifier: EA
  - path to the east texure 
* Floor color: F 220,100,0
  - identifier: F
  - R,G,B colors in range [0,255]: 0, 255, 255
* Ceiling color: C 220,100,0
  - identifier: C
  - R,G,B colors in range [0,255]: 0, 255, 255
		 	 	 		
## The Raycaster specs and requirements

* The miniLibX library must be used.  
* The management of your window must remain smooth: changing to another window, minimizing, etc. 
*Display different wall textures (the choice is yours) that vary depending on which side the wall is facing (North, South, East, West).

* The program must be able to set the floor and ceiling colors to two different ones.
*The program displays the image in a window and respects the following rules: 
* The left and right arrow keys of the keyboard must allow you to look left and right in the maze.
* The W, A, S, and D keys must allow you to move the point of view through the maze
* Pressing ESC must close the window and quit the program cleanly.
* Clicking on the red cross on the window’s frame must close the window and quit the program cleanly.


## Project Overview

* The project is coded in C, adhering to the 42 coding norm.
* To the best of our knowledge, the code is free of memory leaks, crashes, and undefined behavior, no matter how the map file passed as the argument or the path thereof is manipulated and which keys are pressed when “playing” the game.
* The program will crash if the map references an existing .xpm texture file with a wrong structure. Validating the correctness of image files in the XPM format is beyond the scope of the project


### Code Structure:

* src/: Contains the source code files
* Makefile: Build instructions for compiling and running the programs.
* README.md: This file 

Here’s the link to the original GitHub repo that we used during development: 
https://github.com/Tegerrr/cub3d 