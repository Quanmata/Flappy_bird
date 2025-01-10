# Flappy Bird Game - Setup and Run Guide

This document provides detailed instructions on setting up, running, and debugging the Flappy Bird game project using Python in Visual Studio Code (VSCode).

---

## Prerequisites

1. **Install Python**: Make sure Python is installed on your system.
   - Check the version using:
     ```bash
     python --version
     ```
   - [Download Python](https://www.python.org/downloads/) if not installed.

2. **Install VSCode**: Ensure Visual Studio Code is installed.
   - [Download VSCode](https://code.visualstudio.com/).

3. **Install Python Extension for VSCode**:
   - Open VSCode, press `Ctrl + Shift + X`, search for "Python", and install the extension.

4. **Install Required Libraries**:
   - Install `pygame` for the game development:
     ```bash
     pip install pygame
     ```

---

## Running the Game

### 1. Run Directly in VSCode

1. Open the main Python file of your game (e.g., `flappyBird.py`) in VSCode.
2. Press `F5` to run the file in debug mode or `Ctrl + F5` to run without debugging.

### 2. Run via Terminal

1. Open the terminal in VSCode (`Ctrl + `).
2. Navigate to the directory containing `flappyBird.py`:
   ```bash
   cd path/to/your/project
   ```
3. Run the game:
   ```bash
   python flappyBird.py
   ```

---

## Debugging the Game in VSCode

### Setting Up Debug Configuration
1. Open the debug configuration file by pressing `Ctrl + Shift + P` and selecting **"Debug: Open launch.json"**.
2. Choose **Python** when prompted.
3. Replace the content of `launch.json` with the following:

   ```json
   {
       "version": "0.2.0",
       "configurations": [
           {
               "name": "Run Flappy Bird",
               "type": "debugpy",
               "request": "launch",
               "program": "${workspaceFolder}/flappyBird.py",
               "console": "integratedTerminal"
           }
       ]
   }
   ```

4. Save the file and press `F5` to debug your game.

---

## Troubleshooting

### 1. Module Not Found Error (`pygame`):
- Ensure `pygame` is installed in your Python environment:
  ```bash
  pip install pygame
  ```

### 2. Terminal Shows `debugpy` Required:
- Install `debugpy` using:
  ```bash
  pip install debugpy
  ```

### 3. Game Window Closes Immediately:
- Ensure your game loop is implemented correctly. Below is a minimal example:
  ```python
  import pygame
  import sys

  pygame.init()
  screen = pygame.display.set_mode((800, 600))
  pygame.display.set_caption("Flappy Bird")

  running = True
  while running:
      for event in pygame.event.get():
          if event.type == pygame.QUIT:
              running = False

      screen.fill((135, 206, 235))  # Sky blue
      pygame.display.flip()

  pygame.quit()
  sys.exit()
  ```

---

## Additional Notes
- Always activate your virtual environment (if used) before running the game:
  ```bash
  .venv\Scripts\activate
  ```

Use PowerShell with administator run this command line if above is error.
  Set-ExecutionPolicy RemoteSigned -Scope CurrentUser

- Use `Ctrl + Shift + D` in VSCode to manage and run your debug configurations easily.

Feel free to reach out if you encounter issues while setting up or running the game!

