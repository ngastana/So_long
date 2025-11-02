# 🧩 so_long

In this project I simple 2D game using the **MiniLibX** graphical library.  
The goal: make a small top-down game where your player collects items, avoids traps (if any), and escapes the map — all rendered in your own pixel world 🎮  
As images I use Ivan and Iker's faces, because they have helped me and they did everything easier.

---

## 🧠 Project Overview

You’ll write a program that:
- Loads a map from a file (`.ber` extension).  
- Displays the map using images (walls, collectibles, player, exit).  
- Allows the player to move using keyboard input.  
- Tracks and displays the number of moves.  
- Ends the game when the player collects everything and reaches the exit.

Example goal:  
Collect all coins 💰 → Find the exit 🚪 → Win! 🏆  

Your map file (`.ber`) is made of specific characters:

| Symbol | Meaning |
|---------|----------|
| `1` | Wall 🧱 |
| `0` | Empty floor |
| `C` | Collectible 💰 |
| `E` | Exit 🚪 |
| `P` | Player 🧍 |

Example map:
111111
1P0C01
1000E1
111111

### Rules:
- The map must be **rectangular**.  
- Surrounded by walls (`1`) on all sides.  
- Contains **exactly one** player (`P`) and at least **one collectible (`C`)** and **one exit (`E`)**.  
- Must be **solvable** — player can reach all collectibles and the exit.

---

## 🕹️ Gameplay Example

### 🔨 Compilation
```bash
make
```
This will create the executable so_long.
▶️ Run example
```bash
./so_long maps/example.ber
```
## 🎮 Controls
Key	Action
W / ↑	Move up
A / ←	Move left
S / ↓	Move down
D / →	Move right
ESC	Exit game
Each valid move increases your move counter, displayed in the terminal or on-screen.
## 🧰 Example Output
    Moves: 1
    Moves: 2
    Moves: 3
    And visually, your game window might look like:
    🧱🧱🧱🧱🧱🧱
    🧱🧍⬜💰⬜🧱
    🧱⬜⬜⬜🚪🧱
    🧱🧱🧱🧱🧱🧱
## ⚙️ Allowed Functions
You’ll mostly rely on:
open, close, read, write, malloc, free, exit
mlx_init, mlx_new_window, mlx_put_image_to_window,
mlx_xpm_file_to_image, mlx_destroy_window, mlx_loop, mlx_key_hook
…and, of course, your libft functions to handle strings, map parsing, etc.
## 💥 Error Handling
  ❌ Invalid map → print "Error\nInvalid map"
  🚫 Missing elements (player, exit, collectibles) → print an error and exit.
  📉 Non-rectangular or open map → print an error and exit.
  🧹 Free all allocated memory before exiting (no leaks!).
