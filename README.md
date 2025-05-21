# 🕹️ Tower Defense Game — Assignment 3: Closing the Game Loop

This is my interpretation of a tower defense game built using C++, OpenGL, and FreeType. This version adds enhanced gameplay functionality including rotating towers, procedurally generated maps, game over screens, and in-game font rendering.

---

## 🎮 Features Overview

### ✅ FreeType Font Integration
- Integrated FreeType fonts into the game using the provided `SimpleGL` code.
- Successfully merged `font-init` and `renderText` functions into the rendering pipeline.
- Fonts are used to display game information on the intro screen and during gameplay.
- Font resources (`.ttf` files) are stored in the `data/fonts/` folder.

### 🧾 Intro Screen
- Displays the game title, author name, and a dynamic menu.
- Menu options include:
  - Game name
  - Selected game level (updates with number keys 0–9)
  - `SPACE` to start the selected level
  - `G` to generate a random valid level
  - `R` to restart the current level (only works during gameplay)
  - `ESC` to exit the game or return to the intro screen

### 🧾 Game Over Screens
- Victory screen appears when all invaders are destroyed.
- Defeat screen appears when any invader reaches the exit.
- Both screens fade in and display respective messages.
- Pressing `ESC` returns the player to the intro screen.

### 🗺️ Procedural Map Generation
- Pressing `G` on the intro screen generates a new, unique map.
- Each map includes a valid path between start and exit tiles.
- Implemented map validation to ensure only valid levels can be played.
- **Map Generation Algorithm**: Utilized randomized depth-first search (DFS) to carve a valid path through a grid. Surrounding tiles were selectively randomized to ensure path integrity and tower placement flexibility.

### 🏆 Game Score Display
- Displays score in the top-left corner using FreeType fonts.
- Score updates in real-time as invaders are destroyed.

### 🛡️ Tower Placement
- Players can place towers using the **left mouse button**.
- Towers can be removed with the **right mouse button**.
- Towers cannot be placed on path tiles or the top row.

### 🎯 Rotating Towers
- Towers rotate smoothly to aim at the closest invader within a 5-tile radius.
- Towers only fire when aligned and cooldowns are complete.
- Partial marks awarded if rotation is instant — full rotation was implemented.

### ❌ Invalid Level Handling
- Invalid level files (levels 0–9) show an error message on the intro screen if no valid path exists.
- Procedurally generated levels are always validated before starting.

### 👾 Invader Spawning Mechanic
- Spawns `10 × (current level + 1)` invaders.
- Three types of invaders with distinct health and speed.
- "Unspawned: XXX" counter shown at the top of the screen.
- Spawn behavior adapted from A1/A2 with randomized stats and visual variation.

### 💰 Invader Points System
- Each invader is assigned a points value (1–5) on spawn.
- Points are displayed above each invader's head using FreeType.
- When destroyed, points float upward and are added to the player’s score.

### 💥 Animations
- Integrated animated explosion effects triggered when invaders are destroyed by towers.
- Added Invader walking animations.

---

## 🛠️ Development Notes

- Managed shader state to allow clean FreeType rendering alongside game assets.
- Used OpenGL for rendering and SDL for input and window management.

---

## 📝 License

Based on UBC CPSC 427 assignment structure with heavy modification to rendering, logic flow, and UI.
Educational use only. All assets used belong to their respective creators and are included for academic purposes.

