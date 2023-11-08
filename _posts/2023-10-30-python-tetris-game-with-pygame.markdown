---
title: "Let's Play Tetris with Pygame: A Beginner's Guide"
date: 2023-10-30
---

Welcome to PyMakers, where we bring you exciting Python projects! In this blog post, we're going to explore the creation of the classic game "Tetris" using the Pygame library. We'll walk through the code and explain how it works, step by step. Additionally, we'll offer some suggestions on how to improve and expand this basic concept.

<img src="/assets/tetris.gif" alt="Tetris game gif">

### **Setting up the Environment**

Before we delve into the Tetris game, we need to import the Pygame library and initialize it.

```python
import pygame
import random

# Initialize Pygame
pygame.init()
```

### **Constants and Game Setup**

We define some constants for the game window's dimensions and block size. We also set up color constants for the game's visual elements.

```python
WIDTH, HEIGHT = 300, 600
BLOCK_SIZE = 30
WHITE = (255, 255, 255)
BLACK = (0, 0, 0)
```

Next, we create the game window and set its title.

```python
# Create the game window
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Tetris")
```

### **Defining Tetris Shapes (Tetriminos)**

Tetriminos are the fundamental building blocks of Tetris. We define a list of Tetriminos, each represented as a list of lists containing ones and zeros. Ones represent occupied blocks, while zeros represent empty spaces.

```python
# Define Tetris shapes (Tetriminos)
tetriminos = [
    [[1, 1, 1, 1]],
    [[1, 1], [1, 1]],
    [[1, 1, 1], [0, 1, 0]],
    [[1, 1, 1], [1, 0, 0]],
    [[1, 1, 1], [0, 0, 1]],
    [[1, 1, 1], [0, 1, 0], [0, 1, 0]],
    [[1, 1, 1], [1, 0, 0], [1, 0, 0]]
]
```

### **Creating the Game Board**

We set up the game board as a 2D list, with each element representing a block in the grid. A value of 1 represents an occupied block, while 0 represents an empty space.

```python
# Create the game board
board = [[0] * (WIDTH // BLOCK_SIZE) for _ in range(HEIGHT // BLOCK_SIZE)]
```

### **Initializing the Current Tetrimino**

We randomly select a Tetrimino from the list and initialize its position on the game board.

```python
# Initialize the current Tetrimino
current_tetrimino = random.choice(tetriminos)
current_x = WIDTH // BLOCK_SIZE // 2 - len(current_tetrimino[0]) // 2
current_y = 0
```

### **Functions for User Input**

We define functions to handle user input, allowing the player to move the Tetriminos left, right, rotate them, and move them down.

```python
def move_left():
    # Code for moving the Tetrimino left

def move_right():
    # Code for moving the Tetrimino right

def rotate():
    # Code for rotating the Tetrimino

def move_down():
    # Code for moving the Tetrimino down
```

### **Collision Detection**

We implement a function to check for collisions when moving Tetriminos. This function ensures that the Tetriminos do not move into occupied spaces or beyond the game board boundaries.

```python
def check_collision():
    # Code for collision detection
```

### **Placing Tetriminos on the Board**

We have a function to place a Tetrimino on the game board when it lands. This function updates the board by setting the occupied blocks to 1.

```python
def place_tetrimino():
    # Code for placing the Tetrimino on the board
```

### **Clearing Completed Rows**

When a row is completely filled with Tetriminos, we clear it. This function removes the filled rows and adds new empty rows at the top.

```python
def clear_rows():
    # Code for clearing completed rows
```

### **Game Loop**

The game loop handles user input, gravity (moving Tetriminos down automatically), clearing rows, and drawing the game board.

```python
running = True
clock = pygame.time.Clock()
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
        if event.type == pygame.KEYDOWN:
            if event.key == pygame.K_LEFT:
                move_left()
            if event.key == pygame.K_RIGHT:
                move_right()
            if event.key == pygame.K_UP:
                rotate()
            if event.key == pygame.K_DOWN:
                move_down()

    # Gravity - move the Tetrimino down at a constant speed
    move_down()

    # Clear completed rows
    clear_rows()

    # Draw the game board
    screen.fill(BLACK)
    for y, row in enumerate(board):
        for x, value in enumerate(row):
            if value:
                pygame.draw.rect(screen, WHITE, (x * BLOCK_SIZE, y * BLOCK_SIZE, BLOCK_SIZE, BLOCK_SIZE))

    # Draw the current Tetrimino
    for y, row in enumerate(current_tetrimino):
        for x, value in enumerate(row):
            if value:
                pygame.draw.rect(screen, WHITE, ((current_x + x) * BLOCK_SIZE, (current_y + y) * BLOCK_SIZE, BLOCK_SIZE, BLOCK_SIZE))

    pygame.display.update()
    clock.tick(5)  # Adjust this value for the desired speed

pygame.quit()
```

### **Suggestions for Improvement**

This basic Tetris game is a great starting point, but there are numerous ways to enhance and expand it:

1. **Scoring:** Add a scoring system to track and display the player's score based on cleared rows.

2. **Levels:** Implement increasing difficulty levels by adjusting the speed of the Tetrimino's descent.

3. **Next Tetrimino:** Display the next Tetrimino that will appear, allowing players to plan their moves.

4. **Hold Function:** Let players temporarily store a Tetrimino to use later, adding a strategic element to the game.

5. **Sound Effects and Music:** Enhance the gaming experience with audio effects and background music.

6. **High Score:** Save and display high scores for players to compete against.

7. **Game Over Screen:** Create a game over screen with the player's score and an option to restart the game.

8. **Different Tetrimino Sets:** Include various sets of Tetriminos, giving the game more variety.

9. **Power-Ups:** Add power-ups that can help or hinder the player's progress.

10. **Customization:** Allow players to choose their preferred Tetrimino skin or background.

Remember, game development is all about creativity and experimentation. Feel free to explore and add your own unique features to make your Tetris game stand out. Happy coding and happy gaming!