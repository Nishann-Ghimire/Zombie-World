# Zombie World

A 2D top-down shooter built with **C++ and SFML**, featuring directional player movement, projectile-based combat, enemy pursuit, health management, and a custom graphical menu.

Navigate the arena, avoid incoming enemies, and eliminate them using directional shooting. The project explores the fundamentals of game development, including real-time input handling, sprite rendering, object-oriented design, and collision detection.

## Overview

Adventure Game is a desktop game project developed in C++ using the Simple and Fast Multimedia Library (SFML). The game renders a grass-textured arena with environmental obstacles, a controllable player character, enemies that pursue the player, and projectiles fired in the player's current direction.

The project is a work in progress, with the core gameplay loop and several game systems implemented.

## Features

- **Real-time movement:** Control the player using WASD or the arrow keys.
- **Directional shooting:** Fire projectiles in the direction the player is facing.
- **Enemy pursuit:** Enemies track and move toward the player's position.
- **Collision detection:** Detect projectile-enemy and player-enemy collisions.
- **Health management:** Display a health bar and reduce player health after enemy contact.
- **Graphical main menu:** Start the game from a custom menu with image-based buttons.
- **Textured game world:** Render a tiled grass environment with rock and bush obstacles.
- **Custom visual assets:** Use character sprites, enemy animations, projectiles, and menu graphics.
- **C++ object-oriented structure:** Organize game entities and gameplay logic into classes.

## Tech Stack

| Technology | Purpose |
|---|---|
| C++17 | Core programming language |
| SFML | Graphics, window management, input handling, and rendering |
| GNU G++ | C++ compiler |
| GNU Make | Build automation |

## Getting Started

### Prerequisites

You'll need:

- A C++ compiler with C++17 support, such as G++.
- GNU Make.
- SFML 2.x development libraries.
- A desktop environment capable of opening graphical windows.

### 1. Install dependencies

On Ubuntu or Debian-based Linux distributions:

```bash
sudo apt update
sudo apt install build-essential make libsfml-dev
```

The code uses SFML 2-style APIs. Make sure your installed SFML version is compatible with the project.

### 2. Clone the repository

```bash
git clone https://github.com/Nishann-Ghimire/CPP-Project.git
cd CPP-Project
```

### 3. Configure asset paths

The current implementation uses absolute image paths defined by `IMG_PATH` in:

- `src/header.hpp`
- `src/menu.hpp`

Update both definitions to point to the `images` directory inside your cloned repository.

For example, if you cloned the project into `/home/your-user/CPP-Project`, use:

```cpp
#define IMG_PATH "/home/your-user/CPP-Project/images"
```

Replace the example path with the actual location on your computer. Both definitions must point to the same asset directory.

> **Note:** Replacing these machine-specific paths with a portable, relative asset path is a planned improvement.

### 4. Build the project

Compile the game using the included Makefile:

```bash
make
```

The compiled executable will be generated at:

```text
bin/main
```

### 5. Run the game

```bash
make run
```

Alternatively, run the compiled executable directly:

```bash
./bin/main
```

The game opens in a 720 × 720 window.

## Controls

| Action | Input |
|---|---|
| Move up | `W` or `↑` |
| Move down | `S` or `↓` |
| Move left | `A` or `←` |
| Move right | `D` or `→` |
| Shoot | `Left Ctrl`, `Right Ctrl`, or left mouse button |
| Start from the menu | Click the Play button |
| Close the game | Close the game window |

Projectiles travel in the direction the player is facing. The game currently uses a fixed movement speed and a shooting cooldown.

## Project Structure

```text
CPP-Project/
├── images/                 # Textures and graphical assets
│   ├── dave.png            # Player sprite
│   ├── enemy.png           # Enemy sprite
│   ├── bullet.png          # Projectile texture
│   ├── greengrass.jpg      # Arena background texture
│   ├── rock.png            # Rock texture
│   ├── bush.png            # Bush texture
│   └── ...                 # Directional sprites and menu assets
├── src/
│   ├── main.cpp            # Game loop, updates, rendering, collisions
│   ├── header.hpp          # Shared includes and direction definitions
│   ├── character.hpp       # Base character definition
│   ├── player.hpp          # Player movement and health
│   ├── Enemy.hpp           # Enemy behavior and enemy collection
│   ├── bullet.hpp          # Projectile behavior and bullet collection
│   ├── menu.hpp            # Main menu and graphical buttons
│   ├── GameControl.hpp     # Experimental game-control implementation
│   └── level1.hpp          # In-progress level-related logic
├── bin/                    # Compiled executable output
├── Makefile                # Build and run commands
└── plan.md                 # Development checklist
```

## How It Works

The game follows a straightforward real-time game loop:

1. **Process events:** Handle window events, including closing the game.
2. **Read player input:** Update the player's position and facing direction.
3. **Handle shooting:** Create projectiles when the shooting input is held and the cooldown permits it.
4. **Update enemies:** Move enemies toward the player's position.
5. **Check collisions:** Detect projectile hits and player-enemy contact.
6. **Render the scene:** Draw the background tiles, obstacles, player, health bar, enemies, and projectiles.

The main implementation is in `src/main.cpp`, while player, enemy, projectile, and menu logic is organized into their respective classes and headers.

## Current Development Status

The project already contains the foundations of a playable top-down shooter, but it is not yet a complete game.

Areas for further development include:

- More reliable collision handling with obstacles and arena boundaries.
- Completing enemy combat, health, and defeat behavior.
- Additional levels with distinct layouts and progression.
- Working menu actions for sound and exit.
- Improved resource management and frame-rate-independent movement.
- Portable asset loading and clearer separation of gameplay systems.

See [`plan.md`](plan.md) for the project's development checklist.

## Contributing

Contributions and suggestions are welcome. To experiment with the project:

1. Fork the repository.
2. Create a branch for your changes.
3. Implement and test your changes locally.
4. Submit a pull request describing what changed.

## License

No license has been specified yet. Unless a license is added to the repository, permission to reuse or redistribute this project's code and assets should not be assumed.

---

**Built with C++ and SFML**  
Repository: [Nishann-Ghimire/CPP-Project](https://github.com/Nishann-Ghimire/CPP-Project)
