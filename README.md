# Color Catcher

**Color Catcher** is a 2D real-time game developed as a team project for the Computer Graphics and Image Processing course at Metropolitan University, Sylhet. The game is built with **C++**, **OpenGL**, and **GLUT**.

The player controls a colored basket at the bottom of the screen and catches falling balls. A catch scores points only when the basket color matches the ball color. The game combines a simple color-matching mechanic with glow effects, ball trails, particle explosions, combo scoring, and a space-themed background.

> **Academic project:** This repository is intended for educational use and demonstrates practical computer graphics, animation, input handling, collision detection, and particle effects.

## Team

| Member | Student ID |
| --- | --- |
| Mushrefa Chowdhury Nubah | 222-115-104 |
| Abira Haydar Luthfa | 222-115-094 |

## Gameplay

- Colored balls fall from the top of the screen.
- Move the basket horizontally to catch the balls.
- Match the basket color with the falling ball to score.
- Consecutive successful catches increase the combo multiplier.
- Missing a ball or catching it with the wrong color costs one life.
- Each game starts with three lives.

## Controls

| Key | Action |
| --- | --- |
| Left Arrow | Move the basket left |
| Right Arrow | Move the basket right |
| `R` | Change the basket to red |
| `G` | Change the basket to green |
| `B` | Change the basket to blue |
| `Esc` | Exit the game |

## Features

- RGB color-matching gameplay
- Combo-based scoring
- Falling-ball animation and collision detection
- Glowing balls and basket using alpha blending
- A 15-point ball trail
- 50-particle explosion effect after a successful catch
- Floating `+Score` and `MISS!` feedback text
- Procedurally generated stars, shooting stars, moon, and nebula clouds
- Screen shake feedback for catches and misses
- Three lives per game

## Technology

- **C++** — game logic and animation
- **OpenGL** — 2D rendering
- **GLUT** — window management, keyboard input, and timer callbacks
- **GL blending** — transparency and glow effects
- **`std::vector`** — trails and particle collections
- **`rand()` / `time()`** — procedural object and ball spawning

## Technical overview

The game uses an orthographic 2D view with a 600 × 500 coordinate space. A timer callback runs approximately every 30 milliseconds to update the game state:

1. Update the falling ball, trail, particles, floating text, and screen shake.
2. Detect when the ball reaches the basket area.
3. Check the basket position and compare the ball and basket colors.
4. Update the score, combo, or remaining lives.
5. Render the background, basket, ball, particles, and HUD in order.

Glow effects are created by drawing multiple transparent layers. The ball trail is capped at 15 points, and particle effects are limited to 50 particles per successful catch.

## Project files

The repository includes the following project materials:

| File | Description |
| --- | --- |
| `222-115-104, 094_ColorCatcher_CGIP_Project (1).zip` | Project archive containing the presentation, demo video, and code report |
| `222-115-104, 094_ColorCatcher_CGIP_Project (1)/222-115-104, 094_ColorCatcher_Presentation_CGIP(PROJECT).pptx` | Project presentation |
| `222-115-104, 094_ColorCatcher_CGIP_Project (1)/222-115-104, 094_ColorCatcher_demovideo.mp4` | Gameplay demonstration video |
| `222-115-104, 094_ColorCatcher_CGIP_Project (1)/222-115-104, 094_Color_catcher_code.pdf` | PDF containing the project source code |

## Running the project

The repository currently stores the implementation in the code PDF and project archive rather than as a standalone `.cpp` file. To run the game:

1. Extract the project archive.
2. Copy the C++ source from `222-115-104, 094_Color_catcher_code.pdf` into a source file such as `color_catcher.cpp`.
3. Install a C++ compiler and the OpenGL and GLUT development libraries.
4. Compile and link the source using the command appropriate for your operating system.

Example command on Linux:

```bash
g++ color_catcher.cpp -o color_catcher -lGL -lGLU -lglut
./color_catcher
```

On Windows or macOS, configure the equivalent OpenGL and GLUT libraries in your compiler or IDE.

## Future improvements

Possible extensions include difficulty scaling, sound effects, texture mapping, saved high scores, power-ups, and support for multiple simultaneous ball colors.
