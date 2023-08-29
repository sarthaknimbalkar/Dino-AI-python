# Web Dino Game RL Environment

This repository contains code for a custom reinforcement learning environment based on the Chrome Dinosaur Game (T-Rex Runner). The environment is designed for training reinforcement learning agents to play the game using various algorithms.

The environment is built using Python and utilizes popular libraries like `torch`, `pydirectinput`, `mss`, `cv2`, and `gym`. It provides an interface for interacting with the game, capturing frames, and defining the observation space and action space for reinforcement learning.

## Features

- **Custom Environment:** The `WebGame` class is a custom OpenAI Gym-like environment that simulates the Chrome Dinosaur Game. It provides methods for stepping through the environment, resetting, rendering frames, and more.

- **Observation Space:** The environment's observation space is a grayscale image of the game frame, resized to (100, 83) pixels.

- **Action Space:** The action space consists of three discrete actions: jumping, ducking, and no-op (no operation).

- **Capture and Preprocessing:** The environment captures game frames using the `mss` library, preprocesses the frames by converting them to grayscale, resizing them, and providing them as observations to the agent.

## Installation

To use this environment, you need to install the required dependencies. You can install them using the following commands:

```bash
pip install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu113
pip install stable-baselines3[extra] protobuf==3.20.*
pip install mss pydirectinput pytesseract
```

## Usage

1. Clone this repository to your local machine.
2. Create a Python script or Jupyter Notebook to interact with the environment.
3. Instantiate the `WebGame` environment, and use the standard Gym API to interact with it. For example:

```python
from custom_environment import WebGame
import time

# Create the environment
env = WebGame()

# Reset the environment to start a new episode
observation = env.reset()

# Step through the environment for a few time steps
for _ in range(100):
    action = env.action_space.sample()  # Replace with your agent's action
    observation, reward, done, info = env.step(action)
    env.render()
    time.sleep(0.05)  # Optional delay to visualize the game

# Close the environment
env.close()
```

## Customization

You can modify the environment to suit your needs, such as adjusting frame capturing parameters, modifying the observation space, or changing the reward function.

## Acknowledgments

This project was inspired by the Chrome Dinosaur Game and built upon various open-source libraries and resources. It serves as a foundation for developing reinforcement learning agents capable of playing the game effectively.

Feel free to use, modify, and build upon this code to explore reinforcement learning techniques and train agents to play the Chrome Dinosaur Game.
