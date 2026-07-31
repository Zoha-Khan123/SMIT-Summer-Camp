# 📘 Lecture 14: Snake Game with Pygame
## 🐍 Build Your First Classic Snake Game!

Welcome to Python Summer Camp Class 14!

In this lecture, we will create a **complete Snake Game** using pygame!

In **Class 12**, we learned about the **pygame module** and how to create windows and draw shapes. Now we'll use all our Python knowledge to build a real, playable game!

---

# 🎮 What is Snake Game?

The Snake Game is a classic arcade game where:

- 🐍 You control a snake that moves around the screen
- 🍎 The snake eats food to grow longer
- 💀 If the snake hits the wall or itself, the game ends
- 🏆 Your goal is to get the highest score!

---

# 🎯 Game Features

✅ Snake movement with arrow keys  
✅ Food spawns randomly  
✅ Snake grows when eating food  
✅ Score tracking  
✅ Wall collision detection  
✅ Self-collision detection  
✅ Smooth gameplay  

---

# 📦 Prerequisites

Before running this game, you need **pygame** installed.

## Installing pygame with uv

From **Class 12**, we learned how to use `uv` to manage packages.

```bash
# Create project folder
mkdir snake_game
cd snake_game

# Initialize project
uv init

# Add pygame
uv add pygame
```

---

# 🎮 Complete Snake Game Code

Create a file named `snake_game.py`:

```python
import pygame
import random

# Initialize Pygame
pygame.init()

# Screen Settings
WIDTH = 600
HEIGHT = 400
BLOCK_SIZE = 20

screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Snake Game")

# Colors
WHITE = (255, 255, 255)
GREEN = (0, 200, 0)
RED = (255, 0, 0)
BLACK = (0, 0, 0)

# Clock
clock = pygame.time.Clock()
FPS = 10

# Font
font = pygame.font.SysFont(None, 35)


def draw_score(score):
    text = font.render(f"Score: {score}", True, BLACK)
    screen.blit(text, (10, 10))


def game():

    snake = [(100, 100)]
    direction = "RIGHT"

    food_x = random.randrange(0, WIDTH, BLOCK_SIZE)
    food_y = random.randrange(0, HEIGHT, BLOCK_SIZE)

    score = 0

    running = True

    while running:

        # Events
        for event in pygame.event.get():

            if event.type == pygame.QUIT:
                running = False

            if event.type == pygame.KEYDOWN:

                if event.key == pygame.K_UP and direction != "DOWN":
                    direction = "UP"

                elif event.key == pygame.K_DOWN and direction != "UP":
                    direction = "DOWN"

                elif event.key == pygame.K_LEFT and direction != "RIGHT":
                    direction = "LEFT"

                elif event.key == pygame.K_RIGHT and direction != "LEFT":
                    direction = "RIGHT"

        # Head Position
        head_x, head_y = snake[0]

        if direction == "UP":
            head_y -= BLOCK_SIZE

        elif direction == "DOWN":
            head_y += BLOCK_SIZE

        elif direction == "LEFT":
            head_x -= BLOCK_SIZE

        elif direction == "RIGHT":
            head_x += BLOCK_SIZE

        new_head = (head_x, head_y)

        # Wall Collision
        if (
            head_x < 0
            or head_x >= WIDTH
            or head_y < 0
            or head_y >= HEIGHT
        ):
            break

        # Self Collision
        if new_head in snake:
            break

        snake.insert(0, new_head)

        # Food Collision
        if head_x == food_x and head_y == food_y:

            score += 1

            food_x = random.randrange(0, WIDTH, BLOCK_SIZE)
            food_y = random.randrange(0, HEIGHT, BLOCK_SIZE)

        else:
            snake.pop()

        # Draw
        screen.fill(WHITE)

        pygame.draw.rect(
            screen,
            RED,
            (food_x, food_y, BLOCK_SIZE, BLOCK_SIZE)
        )

        for block in snake:
            pygame.draw.rect(
                screen,
                GREEN,
                (block[0], block[1], BLOCK_SIZE, BLOCK_SIZE)
            )

        draw_score(score)

        pygame.display.flip()

        clock.tick(FPS)

    pygame.quit()


if __name__ == "__main__":
    game()
```

---

# 💻 How to Run the Game

```bash
# Using uv (recommended)
uv run snake_game.py

# Or using python directly
python snake_game.py
```

---

# 🔍 Detailed Code Explanation

Let's break down every part of the code!

---

## 📦 Part 1: Importing Modules

```python
import pygame
import random
```

### Explanation:

- **pygame**: The module we learned in Class 12 for creating games
- **random**: Built-in module (Class 12) for generating random food positions

---

## 🎨 Part 2: Initialize Pygame

```python
pygame.init()
```

### Explanation:

This line **initializes all pygame modules**.

Without this, pygame won't work properly.

**Think of it like:** Turning on the game engine before starting.

---

## 📺 Part 3: Screen Settings

```python
WIDTH = 600
HEIGHT = 400
BLOCK_SIZE = 20

screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Snake Game")
```

### Explanation:

**WIDTH = 600**
- Screen width in pixels

**HEIGHT = 400**
- Screen height in pixels

**BLOCK_SIZE = 20**
- Size of each snake block and food
- Snake moves in increments of 20 pixels

**screen = pygame.display.set_mode((WIDTH, HEIGHT))**
- Creates the game window
- Learned in Class 12

**pygame.display.set_caption("Snake Game")**
- Sets the window title

### Visual Representation:

```
┌─────────────────────────┐
│  Snake Game        ─ □ ×│  ← Window Title
├─────────────────────────┤
│                         │
│   600 pixels wide       │  ← Game Area
│   400 pixels high       │
│                         │
└─────────────────────────┘
```

---

## 🎨 Part 4: Colors

```python
WHITE = (255, 255, 255)
GREEN = (0, 200, 0)
RED = (255, 0, 0)
BLACK = (0, 0, 0)
```

### Explanation:

Colors use **RGB** format (Red, Green, Blue) - learned in Class 12.

Each color has values from 0 to 255.

| Color | RGB Values | Used For |
|-------|------------|----------|
| WHITE | (255, 255, 255) | Background |
| GREEN | (0, 200, 0) | Snake body |
| RED | (255, 0, 0) | Food |
| BLACK | (0, 0, 0) | Score text |

---

## ⏱️ Part 5: Clock and FPS

```python
clock = pygame.time.Clock()
FPS = 10
```

### Explanation:

**clock = pygame.time.Clock()**
- Creates a clock object to control game speed

**FPS = 10**
- **FPS** = Frames Per Second
- Game updates 10 times per second
- Higher FPS = Faster game, Lower FPS = Slower game

**Why 10 FPS?**
- Makes the snake move at a comfortable speed
- Not too fast, not too slow

---

## 🔤 Part 6: Font

```python
font = pygame.font.SysFont(None, 35)
```

### Explanation:

- Creates a font for displaying text
- `None` = Use default system font
- `35` = Font size

Used to display the score on screen.

---

## 📊 Part 7: Draw Score Function

```python
def draw_score(score):
    text = font.render(f"Score: {score}", True, BLACK)
    screen.blit(text, (10, 10))
```

### Explanation:

This is a **user-defined function** (Class 11).

**font.render(f"Score: {score}", True, BLACK)**
- Creates text to display
- Uses f-string (Class 06) to show score
- `True` = Anti-aliasing (smooth text)
- `BLACK` = Text color

**screen.blit(text, (10, 10))**
- Draws text on screen at position (10, 10)
- Top-left corner

### Visual:

```
┌─────────────────────┐
│ Score: 5            │  ← Position (10, 10)
│                     │
│      🐍             │
│                     │
└─────────────────────┘
```

---

## 🎮 Part 8: Main Game Function

```python
def game():
```

This function contains all the game logic!

Let's break it down step by step.

---

## 🐍 Part 9: Initialize Snake

```python
snake = [(100, 100)]
direction = "RIGHT"
```

### Explanation:

**snake = [(100, 100)]**
- Snake is a **list** (Class 08) of tuples
- Each tuple `(x, y)` represents a snake block position
- Initially, snake has only 1 block at position (100, 100)
- This is the **head** of the snake

**direction = "RIGHT"**
- Snake starts moving to the right
- Can be: "UP", "DOWN", "LEFT", "RIGHT"

### Visual:

```
Start Position:
┌─────────────────────┐
│                     │
│   ■                 │  ← Snake at (100, 100)
│                     │
│                     │
└─────────────────────┘
```

---

## 🍎 Part 10: Initialize Food

```python
food_x = random.randrange(0, WIDTH, BLOCK_SIZE)
food_y = random.randrange(0, HEIGHT, BLOCK_SIZE)
```

### Explanation:

Uses **random.randrange()** (Class 12) to generate random positions.

**random.randrange(0, WIDTH, BLOCK_SIZE)**
- Generates random x position
- From 0 to 600, in steps of 20
- Possible values: 0, 20, 40, 60, ..., 580

**Why BLOCK_SIZE step?**
- Ensures food aligns with the grid
- Snake can eat it properly

### Example Values:

```python
food_x = 240  # Random position (multiple of 20)
food_y = 180  # Random position (multiple of 20)
```

---

## 📊 Part 11: Initialize Score

```python
score = 0
```

### Explanation:

- Starts at 0
- Increases by 1 each time snake eats food

---

## 🔄 Part 12: Game Loop

```python
running = True

while running:
```

### Explanation:

This is the **main game loop** (Class 10 - while loop).

The loop continues **as long as** `running` is `True`.

Everything inside this loop runs repeatedly, creating the animation effect.

---

## 🎮 Part 13: Event Handling

```python
for event in pygame.event.get():

    if event.type == pygame.QUIT:
        running = False

    if event.type == pygame.KEYDOWN:

        if event.key == pygame.K_UP and direction != "DOWN":
            direction = "UP"

        elif event.key == pygame.K_DOWN and direction != "UP":
            direction = "DOWN"

        elif event.key == pygame.K_LEFT and direction != "RIGHT":
            direction = "LEFT"

        elif event.key == pygame.K_RIGHT and direction != "LEFT":
            direction = "RIGHT"
```

### Explanation:

**pygame.event.get()**
- Gets all events (mouse clicks, key presses, window close)

**pygame.QUIT**
- When user clicks the X button
- Sets `running = False` to exit game

**pygame.KEYDOWN**
- When a key is pressed

**pygame.K_UP, K_DOWN, K_LEFT, K_RIGHT**
- Arrow key constants

### Important Logic:

**if event.key == pygame.K_UP and direction != "DOWN":**

Why check `direction != "DOWN"`?

**Because**: If snake is moving DOWN, pressing UP would make it go backwards into itself!

This prevents the snake from reversing direction.

### Valid Direction Changes:

| Current Direction | Can Change To |
|-------------------|---------------|
| UP | LEFT, RIGHT (not DOWN) |
| DOWN | LEFT, RIGHT (not UP) |
| LEFT | UP, DOWN (not RIGHT) |
| RIGHT | UP, DOWN (not LEFT) |

---

## 📍 Part 14: Calculate New Head Position

```python
head_x, head_y = snake[0]

if direction == "UP":
    head_y -= BLOCK_SIZE

elif direction == "DOWN":
    head_y += BLOCK_SIZE

elif direction == "LEFT":
    head_x -= BLOCK_SIZE

elif direction == "RIGHT":
    head_x += BLOCK_SIZE

new_head = (head_x, head_y)
```

### Explanation:

**head_x, head_y = snake[0]**
- Gets current head position
- `snake[0]` is the first element (head) of the snake list

**Moving the Snake:**

- **UP**: Decrease y by 20 (move up on screen)
- **DOWN**: Increase y by 20 (move down on screen)
- **LEFT**: Decrease x by 20 (move left)
- **RIGHT**: Increase x by 20 (move right)

**new_head = (head_x, head_y)**
- Creates a new tuple for the new head position

### Visual Example:

```
Original position: (100, 100)
Direction: RIGHT
New position: (120, 100)  ← Moved 20 pixels right

(100, 100) → (120, 100)
    ■            ■
```

---

## 💥 Part 15: Wall Collision Detection

```python
if (
    head_x < 0
    or head_x >= WIDTH
    or head_y < 0
    or head_y >= HEIGHT
):
    break
```

### Explanation:

Checks if snake hit any wall.

**head_x < 0**
- Hit left wall

**head_x >= WIDTH**
- Hit right wall (WIDTH = 600)

**head_y < 0**
- Hit top wall

**head_y >= HEIGHT**
- Hit bottom wall (HEIGHT = 400)

**break**
- Exits the game loop
- Game ends

### Visual:

```
┌─────────────────────┐ ← head_y < 0 (Top wall)
│                     │
│                     │
│                     │
└─────────────────────┘ ← head_y >= HEIGHT (Bottom wall)
↑                     ↑
head_x < 0            head_x >= WIDTH
(Left wall)           (Right wall)
```

---

## 🐍 Part 16: Self Collision Detection

```python
if new_head in snake:
    break
```

### Explanation:

**new_head in snake**
- Checks if the new head position is already in the snake body
- Uses `in` operator (Class 08 - Lists)

**If True:**
- Snake hit itself!
- Game ends with `break`

### Example:

```
Snake body: [(100, 100), (80, 100), (60, 100)]
New head: (80, 100)

(80, 100) is already in snake → Collision! → Game Over
```

---

## ➕ Part 17: Add New Head

```python
snake.insert(0, new_head)
```

### Explanation:

**snake.insert(0, new_head)**
- Inserts new head at the **beginning** of the list (Class 08)
- Index `0` = First position
- Old head becomes part of the body

### Example:

```python
# Before
snake = [(100, 100), (80, 100)]

# New head at (120, 100)
snake.insert(0, (120, 100))

# After
snake = [(120, 100), (100, 100), (80, 100)]
          ↑ New Head  ↑ Old Head  ↑ Body
```

---

## 🍎 Part 18: Food Collision

```python
if head_x == food_x and head_y == food_y:

    score += 1

    food_x = random.randrange(0, WIDTH, BLOCK_SIZE)
    food_y = random.randrange(0, HEIGHT, BLOCK_SIZE)

else:
    snake.pop()
```

### Explanation:

**if head_x == food_x and head_y == food_y:**
- Checks if snake head is at the same position as food
- Uses `and` logical operator (Class 04)

**When Food is Eaten:**

1. **score += 1**
   - Increase score by 1 (Class 04 - Assignment operators)

2. **Generate new food position**
   - Random x and y coordinates
   - Food respawns at a new location

**else: snake.pop()**
- If no food eaten, remove the tail
- **pop()** removes last element (Class 08)
- This keeps snake at the same length when moving

### Key Logic:

**Why pop() in else?**

- We already added a new head with `insert(0, new_head)`
- If we don't eat food, snake shouldn't grow
- So we remove the tail to maintain length

**When Food is Eaten:**
- New head added ✅
- Tail NOT removed ✅
- Result: Snake grows by 1 block! 🐍

**When Food is NOT Eaten:**
- New head added ✅
- Tail removed ✅
- Result: Snake moves without growing 🐍

### Visual Example:

```
Snake eats food:
Before: ■ ■ ■ 🍎
After:  ■ ■ ■ ■   (New head added, tail kept)

Snake doesn't eat food:
Before: ■ ■ ■
After:  ■ ■ ■     (New head added, tail removed)
```

---

## 🎨 Part 19: Drawing Everything

```python
screen.fill(WHITE)

pygame.draw.rect(
    screen,
    RED,
    (food_x, food_y, BLOCK_SIZE, BLOCK_SIZE)
)

for block in snake:
    pygame.draw.rect(
        screen,
        GREEN,
        (block[0], block[1], BLOCK_SIZE, BLOCK_SIZE)
    )

draw_score(score)

pygame.display.flip()
```

### Explanation:

**screen.fill(WHITE)**
- Fills entire screen with white color
- Clears previous frame

**Drawing Food:**

```python
pygame.draw.rect(screen, RED, (food_x, food_y, BLOCK_SIZE, BLOCK_SIZE))
```
- Draws a red rectangle (food)
- Position: (food_x, food_y)
- Size: 20×20 pixels

**Drawing Snake:**

```python
for block in snake:
    pygame.draw.rect(screen, GREEN, (block[0], block[1], BLOCK_SIZE, BLOCK_SIZE))
```
- Uses **for loop** (Class 10) to draw each snake block
- Each block is a green rectangle
- `block[0]` = x position, `block[1]` = y position

**draw_score(score)**
- Calls our custom function to display score

**pygame.display.flip()**
- Updates the entire screen
- Shows all the drawings we made

### Drawing Order (Important!):

```
1. Fill background (WHITE)
2. Draw food (RED)
3. Draw snake (GREEN)
4. Draw score (BLACK text)
5. Update display
```

This order ensures everything appears correctly.

---

## ⏱️ Part 20: Control Game Speed

```python
clock.tick(FPS)
```

### Explanation:

**clock.tick(FPS)**
- Controls how fast the game runs
- `FPS = 10` means 10 frames per second
- Creates a delay to slow down the game loop

**Without this:**
- Game would run at maximum speed
- Snake would move too fast to control!

**With this:**
- Game runs smoothly at controlled speed
- Easy to play

---

## 🏁 Part 21: Game Over

```python
pygame.quit()
```

### Explanation:

**pygame.quit()**
- Closes pygame
- Cleans up resources
- Exits the game

This runs after the game loop ends (collision happened).

---

## 🚀 Part 22: Run the Game

```python
if __name__ == "__main__":
    game()
```

### Explanation:

**if __name__ == "__main__":**
- Special Python condition
- Checks if this file is being run directly (not imported)

**game()**
- Calls the main game function
- Starts the game!

---

# 🎓 Concepts Used in Snake Game

| Concept | Where Used | Class |
|---------|-----------|-------|
| **Modules** | `import pygame, random` | Class 12 |
| **Functions** | `game()`, `draw_score()` | Class 11 |
| **Variables** | `WIDTH`, `snake`, `direction` | Class 03 |
| **Data Types** | Integers, Strings, Booleans | Class 03 |
| **Lists** | `snake = [(100, 100)]` | Class 08 |
| **Tuples** | `(head_x, head_y)` | Class 08 |
| **While Loop** | Main game loop | Class 10 |
| **For Loop** | Drawing snake blocks | Class 10 |
| **Conditionals** | `if-elif-else` | Class 07 |
| **Logical Operators** | `and`, `or` | Class 04 |
| **Comparison Operators** | `==`, `>=`, `<` | Class 04 |
| **Assignment Operators** | `+=`, `=` | Class 04 |
| **Break Statement** | Exit game on collision | Class 10 |
| **String Formatting** | f-strings in score | Class 06 |
| **List Methods** | `insert()`, `pop()` | Class 08 |
| **Random Module** | Random food position | Class 12 |
| **Pygame** | Graphics and game window | Class 12 |

---

# 🎮 How the Game Works (Summary)

## Game Flow:

```
1. Initialize pygame and create window
2. Set up colors, clock, font
3. Start game loop:
   ↓
4. Handle keyboard input (arrow keys)
   ↓
5. Calculate new snake head position
   ↓
6. Check wall collision → If yes → Game Over
   ↓
7. Check self collision → If yes → Game Over
   ↓
8. Add new head to snake
   ↓
9. Check if food eaten:
   → Yes: Increase score, spawn new food
   → No: Remove tail
   ↓
10. Draw everything (background, food, snake, score)
    ↓
11. Update display
    ↓
12. Control speed with clock.tick(FPS)
    ↓
13. Repeat from step 4
```

---

# 🎯 Game Controls

| Key | Action |
|-----|--------|
| ↑ | Move Up |
| ↓ | Move Down |
| ← | Move Left |
| → | Move Right |

---

# 🏆 Challenge Ideas

Try improving the game with these features:

1. **Difficulty Levels**: Increase FPS as score increases
2. **Game Over Screen**: Show "Game Over" message with final score
3. **Restart Option**: Press 'R' to restart after game over
4. **High Score**: Save and display the highest score
5. **Sound Effects**: Add sounds for eating food and collisions
6. **Obstacles**: Add walls or barriers in the middle
7. **Different Food**: Add special food worth more points
8. **Borders**: Add visible borders around the screen

---

# 🐛 Common Errors and Solutions

## Error 1: pygame not installed

```
ModuleNotFoundError: No module named 'pygame'
```

**Solution:**
```bash
uv add pygame
```

## Error 2: Snake moves too fast

**Problem:** FPS value is too high

**Solution:** Change `FPS = 10` to a lower value like `FPS = 8`

## Error 3: Food spawns outside screen

**Problem:** Random range is wrong

**Solution:** Make sure food coordinates use `BLOCK_SIZE` step:
```python
random.randrange(0, WIDTH, BLOCK_SIZE)
```

---

# 📚 Learning Outcomes

After completing this lecture, students can:

✅ Build a complete game from scratch  
✅ Use pygame for game development  
✅ Implement game logic with loops and conditions  
✅ Handle keyboard input  
✅ Detect collisions  
✅ Work with lists and tuples for game state  
✅ Apply all Python concepts learned in previous classes  
✅ Understand game development principles  

---

# 🎉 Congratulations!

You've successfully learned how to build a complete Snake Game using Python and pygame!

This project combines **all the concepts** we learned throughout the Python Summer Camp:

- Variables, data types, operators
- Strings, lists, tuples, dictionaries
- Conditionals and loops
- Functions
- Modules

You are now ready to build even more complex games and applications! 🚀

---

**Happy Gaming! 🎮🐍✨**
