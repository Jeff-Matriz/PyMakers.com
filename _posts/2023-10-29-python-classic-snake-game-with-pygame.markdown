---
title: "Creating the Classic Snake Game with Pygame"
date: 2023-10-29
---

Welcome to PyMakers! In this tutorial, we're going to explore the exciting world of Pygame by building a classic Snake game. Python and Pygame make game development accessible and fun, making it an ideal choice for beginners to start their game development journey.

<img src="/assets/snake.gif" alt="Snake game preview">

### Prerequisites
Before we dive into the code, make sure you have Pygame installed. You can install it using `pip`:

```python
pip install pygame
```

### The Snake Game Basics
The Snake game is a simple yet addictive classic. You control a snake on the screen, and your goal is to eat food to grow while avoiding running into the walls or yourself. Let's break down the main components:

1. **Snake**: The player controls a snake that can move up, down, left, and right. The snake continuously moves forward, and the player's input changes its direction.

2. **Food**: Food items appear randomly on the screen. When the snake consumes the food, it grows longer.

3. **Collision Detection**: You need to check for collisions between the snake's head, the food, and the screen boundaries.

4. **Score Keeping**: Players earn points for each piece of food eaten. We'll display the score on the screen.

Let's dive into the code and break it down step by step:

### **Setting Up the Environment**

First, we import the necessary libraries: pygame, sys, and random.

```python
import pygame
import sys
import random
```

We then initialize the Pygame library.

```python
pygame.init()
```

### **Constants and Game Setup**

Now, we define some constants that will be used throughout the game. These constants set up the game window's dimensions, grid size, colors, and other initial parameters.

```python
WIDTH, HEIGHT = 600, 400
GRID_SIZE = 20
GRID_WIDTH = WIDTH // GRID_SIZE
GRID_HEIGHT = HEIGHT // GRID_SIZE
WHITE = (255, 255, 255)
GREEN = (0, 255, 0)
RED = (255, 0, 0)
```

### **Initializing the Game Window**

We create the game window and set its title.

```python
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Snake Game")
```

### **Snake Initialization**

We set up the snake's initial position and direction.

```python
snake = [(GRID_WIDTH // 2, GRID_HEIGHT // 2)]
snake_direction = (1, 0)
```

### **Food Initialization**

The food is placed randomly on the grid.

```python
food = (random.randint(0, GRID_WIDTH - 1), random.randint(0, GRID_HEIGHT - 1))
```

### **Score and Game Over Variables**

We set up the initial score and the game over flag.

```python
score = 0
game_over = False
```

### **Game Loop**

The game loop is the core of our Snake game. It handles user input, updates the game state, and continuously redraws the screen.

```python
while not game_over:
```

- **Handling User Input**

  We capture user input to control the snake's direction. The arrow keys are used to change the snake's direction.

  ```python
  for event in pygame.event.get():
      if event.type == pygame.QUIT:
          game_over = True
      elif event.type == pygame.KEYDOWN:
          if event.key == pygame.K_UP and snake_direction != (0, 1):
              snake_direction = (0, -1)
          elif event.key == pygame.K_DOWN and snake_direction != (0, -1):
              snake_direction = (0, 1)
          elif event.key == pygame.K_LEFT and snake_direction != (1, 0):
              snake_direction = (-1, 0)
          elif event.key == pygame.K_RIGHT and snake_direction != (-1, 0):
              snake_direction = (1, 0)
  ```

- **Moving the Snake**

  The snake's head is moved according to its current direction.

  ```python
  x, y = snake[0]
  new_head = (x + snake_direction[0], y + snake_direction[1])
  snake.insert(0, new_head)
  ```

- **Collision with Food**

  If the snake's head collides with the food, the player's score is incremented, and new food is generated at a random position.

  ```python
  if snake[0] == food:
      score += 1
      food = (random.randint(0, GRID_WIDTH - 1), random.randint(0, GRID_HEIGHT - 1))
  else:
      snake.pop()
  ```

- **Collision with Wall or Itself**

  We check if the snake collides with the wall or itself. If it does, the game is over.

  ```python
  if (
      (snake[0][0] < 0)
      or (snake[0][0] >= GRID_WIDTH)
      or (snake[0][1] < 0)
      or (snake[0][1] >= GRID_HEIGHT)
      or (snake[0] in snake[1:])
  ):
      game_over = True
  ```

- **Clearing the Screen**

  We clear the screen by filling it with a black background.

  ```python
  screen.fill((0, 0, 0))
  ```

- **Drawing the Snake**

  The snake is drawn by iterating through its segments and creating rectangles for each segment using the `pygame.draw.rect()` function.

  ```python
  for segment in snake:
      pygame.draw.rect(
          screen, GREEN, (segment[0] * GRID_SIZE, segment[1] * GRID_SIZE, GRID_SIZE, GRID_SIZE)
      )
  ```

- **Drawing the Food**

  The food is drawn in a similar manner as the snake.

  ```python
  pygame.draw.rect(
      screen, RED, (food[0] * GRID_SIZE, food[1] * GRID_SIZE, GRID_SIZE, GRID_SIZE)
  )
  ```

- **Updating the Display**

  We update the display to show the changes made in the current game loop iteration.

  ```python
  pygame.display.flip()
  ```

- **Controlling Game Speed**

  We control the game speed by introducing a delay with `pygame.time.delay()`.

  ```python
  pygame.time.delay(100)
  ```

### **Game Over Screen**

After the game loop ends, we display a "Game Over" message with the player's score.

```python
font = pygame.font.Font(None, 36)
game_over_text = font.render(f"Game Over! Score: {score}", True, WHITE)
game_over_rect = game_over_text.get_rect(center=(WIDTH / 2, HEIGHT / 2))
screen.blit(game_over_text, game_over_rect)
pygame.display.flip()
```

### **Final Steps**

We wait for a few seconds before quitting the game to give the player a chance to see the game over message.

```python
pygame.time.delay(2000)
```

Finally, we clean up and quit Pygame.

```python
pygame.quit()
sys.exit()
```

### Conclusion
Congratulations! You've just created a basic Snake game using Pygame. While this tutorial covers the fundamentals, there's so much more you can add, like music, more advanced game mechanics, or a high-score system. This project is a fantastic starting point to explore game development with Python.

Keep experimenting, learning, and improving your game. The world of Pygame offers endless possibilities, and with your newfound knowledge, you can continue creating engaging games and interactive applications. Good luck with your game development journey, and stay tuned for more exciting PyMakers tutorials!

You can get the full source code here: [Classic Snake Game with Pygame](https://github.com/Jeff-Matriz/Pygame/blob/master/snake.py)