# Project 1: Navigation

### Introduction
The task is to train a reinforcement agent to collect yellow bananas in a modified unity environment.

#### Environment
The environment is episodic with a fix duration. Every time the agent picks a banana the environment places a new one of the respective color at a random position. 


#### State Space
The agent's state space comprises it's current velocity along the direction it points and a 36 dimensional ray-based perception system detecting obstacles in front of the agent.

#### State Space
The agent deals with a 4 dimensional action space, corresponding to:
- **`0`** - move forward.
- **`1`** - move backward.
- **`2`** - turn left.
- **`3`** - turn right.

#### Reward
Since the agent should be encouraged to pick up yellow bananas but to leave out blue ones, the agent receives a reward of +1 if it picks a yellow banana and -1 if it collects a blue banana. For all other cases it gets a reward of 0.


### Implementation

#### Files
- `Navigation.ipynb`	(main file for training and validation.)
- `DQN_Agents.py` (deep Q-learning agent, Q-network and replay buffer package)
- `qnetwork_local.pth` (weights of trained Q-network)

#### Dependencies

##### Anaconda Environment

Follow the instructions in https://github.com/udacity/deep-reinforcement-learning section **Dependencies** to set up the anaconda environment.


##### Unity Environment

1. Download and unpack the environment for your operating system from the links below:

    - Linux [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)

    See https://github.com/udacity/deep-reinforcement-learning/blob/master/p1_navigation/README.md for further information.

2. Set the path to the environment binary in `Navigation.ipynb` (code cell 2) according to your environment. For example:
    ```python
    env = UnityEnvironment(file_name="Banana_Linux/Banana.x86_64")
    ```

#### Getting Started
For training run `Navigation.ipynb`. For validation instantiate an agent from `DQN_Agents.py` and load the weights according to 
```python
agent.qnetwork_local.load_state_dict(torch.load('qnetwork_local.pth'))
```
