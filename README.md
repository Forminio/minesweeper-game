# JavaScript Minesweeper Game

[English](README.md) | [简体中文](README.zh-CN.md)

A classic Minesweeper game implemented with pure HTML, CSS and JavaScript.

## Game Features

- 🎮 **Classic Gameplay**: Same rules and experience as the classic Windows Minesweeper game
- 🎚️ **Multiple Difficulty Levels**: Offers beginner (12x12), intermediate (16x16), and advanced (19x19) difficulty options
- 🎯 **Safe First Click**: The first click will never hit a mine
- 🚩 **Flag Marking**: Right-click to mark suspected mine locations
- 🔢 **Number Hints**: Colored numbers showing the count of surrounding mines
- 📱 **Responsive Design**: Adapts to different screen sizes, including mobile devices

## Online Demo

🎮 [Click here to play the game online](https://blog.forminio.cn/sao-lei)

## Game Screenshot

![Minesweeper Game Screenshot](https://cdn.forminio.cn/picx-images-hosting@master/wenzhan/扫雷截图.esqorn3ch.webp)

## Installation and Running

Clone the repository:

```bash
git clone https://github.com/Forminio/minesweeper-game.git
```

## Technical Implementation Details
### 1. Game Core Data Structures
The game uses two two-dimensional arrays as core data structures:
- mineBoard: Records whether each cell is a mine ('M') or a number (0-8)
- showBoard: Records the display state of each cell ('hidden', 'revealed', 'flag', 'mine')

### 2. Mine Generation Algorithm
Key implementation points:

- Uses random numbers to generate mine positions
- Ensures the first click position and its surrounding 8 cells will not have mines
- After placing mines, calculates the number of surrounding mines for each non-mine cell
### 3. Auto-Expansion Algorithm (Recursive Implementation)
Key implementation points:

- Uses a recursive algorithm to automatically expand blank areas
- When clicking on a cell with number 0 (no surrounding mines), automatically expands the surrounding 8 cells
- Recursion continues to expand until number cells are encountered
- Boundary checks ensure no out-of-bounds errors
### 4. Victory Detection Algorithm
Key implementation points:

- Counts the number of revealed cells
- When the number of revealed cells equals the total number of cells minus the number of mines, declares victory
- Automatically marks all unmarked mines upon victory
### 5. Rendering and DOM Operations
Key implementation points:

- Uses CSS Grid layout to implement the game grid
- Dynamically adjusts grid size to accommodate different difficulty levels
- Adds click and right-click events to each cell
- Sets different styles and content based on cell state
### 6. Responsive Design
Key implementation points:

- Uses media queries to adapt to different screen sizes
- Adjusts button layout and cell size on small screen devices
- Ensures the game runs well on mobile devices
### 7. Robustness and Error Handling
Key implementation points:

- Adds multiple event listeners to ensure the game runs normally in various situations
- Periodically checks game state and automatically fixes potential issues
- Handles page visibility changes, cache loading, and other special cases

## Design Highlights
- Classic Windows Style UI: Uses gray background, raised and recessed borders to recreate the visual style of classic Windows Minesweeper
- Colored Number Hints: Different numbers use different colors to improve game readability
- Game State Feedback: Provides game end feedback through modal windows, displaying game results and time
- Adaptive Layout: Game interface can adapt to different screen sizes, providing a good experience on both desktop and mobile devices
