# DRLND Navigation Project

## Project Description

### Environment

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is
provided for collecting a blue banana. Thus, the goal of the agent is to collect
as many yellow bananas as possible while avoiding blue bananas.

### State

The state space has 37 dimensions and contains the agent's velocity, along with
ray-based perception of objects around the agent's forward direction.

Ray Perception (35)

7 rays projecting from the agent at the following angles (and returned in this order):

[20, 90, 160, 45, 135, 70, 110] # 90 is directly in front of the agent

Ray (5)

Each ray is projected into the scene. If it encounters one of four detectable objects the value at that position in the array is set to 1. Finally there is a distance measure which is a fraction of the ray length.

[Banana, Wall, BadBanana, Agent, Distance]

example

[0, 1, 1, 0, 0.2]

There is a BadBanana detected 20% of the way along the ray and a wall behind it.

### Action

Given the state information, the agent has to learn how to best select actions. Four discrete
actions are available, corresponding to:

- 0 - move forward.
- 1 - move backward.
- 2 - turn left.
- 3 - turn right.

Velocity of Agent (2)

Left/right velocity (about -4 to 4)

Forward/backward velocity (about -12.5 to 12.5)

### Aim

The task is episodic, and in order to solve the environment, the agent must get an average score of +13 over 100 consecutive episodes.

## Setup

1. Unzip the required environment for your machine (in this project folder):
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
    - Linux (headless): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux_NoVis.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)
2. Setup virtual environment (inside this project folder)
```
$ virtualenv ENV
$ . ENV/bin/activate
```
3. Install dependencies:
```
$ pip3 install --user jupyter numpy mlagents matplotlib torch
```
4. Run Jupyter Notebook
```
$ jupyter notebook
```
A web-browser with all the required files should open up automatically now.

## Usage

Open `Report.ipynb` notebook in the web-browser (using jupyter notebook) and run
the commands as described in the file.

For training the model, mark the flag `train_flag=True`.
Once proceeding with the code in the notebook file, this setting with train the
model designed and store the weights as `checkpoint.pth`.

For simply testing the performance of the trained model, simply set
`train_flag=False`.
This setting will assume that `checkpoint.pth` is present and test the
respective model's performance, when code in the notebook file is run.

## References

- [1] https://github.com/udacity/deep-reinforcement-learning
- [2] Schaul, T., Quan, J., Antonoglou, I., & Silver, D. (2015). Prioritized experience replay. arXiv preprint arXiv:1511.05952.
- [3] Van Hasselt, H., Guez, A., & Silver, D. (2016, March). Deep reinforcement learning with double q-learning. In Thirtieth AAAI conference on artificial intelligence.
- [4] https://github.com/ltbringer/DRLND_Navigation_Project
- [5] https://github.com/Unity-Technologies/ml-agents/issues/1134#issuecomment-417497502
