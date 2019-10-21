# Continuous Control Project for Udacity DRLND

This project solves Reacher navigation environment created with Unity.

## Environment Description

In this environment, a double-jointed arms can move to target locations. 
A reward of +0.1 is provided for each step that the agent's hand is in the goal location. 
Thus, the goal of the agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of `33` variables corresponding to position, rotation, velocity, and angular velocities of the arm. 

Action space is continuous, each action is a vector with four numbers, corresponding to torque applicable to two joints. 
Every entry in the action vector should be a number between -1 and 1.

Environment contains 20 agents (arms). Environment is considered solved when the average over all agents over 100 episodes exceeds `30`.

## Getting Started

Following steps were tested for **Windows 10** with Anaconda installed. For other OS,
please refer to installation steps in the original [DLRND repo](https://github.com/udacity/deep-reinforcement-learning#dependencies).

1. Install [SWIG](https://sourceforge.net/projects/swig/files/swigwin/swigwin-4.0.1/swigwin-4.0.1.zip/download).
Unpack zip archive to any folder, open "Edit system environment variables", edit `Path` to add folder where `swig.exe` is located.

2. Create new Python environment in Anaconda prompt:
    ```
    conda create --name drlnd python=3.6
    activate drlnd
    conda install pytorch=0.4.0 -c pytorch
    ```

3. Checkout code and install dependencies:
    ```
    activate drlnd
    git clone https://github.com/vvmnnnkv/drlnd-continuous-control
    cd drlnd-continuous-control
    pip install -r requirements.txt
    python -m ipykernel install --user --name drlnd --display-name "drlnd"
    ```

4. Download the [Reacher (20 agents version) environment executable](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)  for Windows and unpack in the project folder.

5. Run jupyter notebook in the project root (this should open browser):
    ```
    jupyter notebook --notebook-dir=.
    ```

## Run Trained Agent
In jupyter, open `Demo.ipynb` and follow instructions.


## Train Agent
In jupyter, open `Train.ipynb` and follow instructions.

