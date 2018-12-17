# Udacity Deep Reinforcment Learning Nanodegree - Project 3 - Collaboration and Competition

This github repository contains a possible solution for the third project of the Udacity Deep Reinforcment Learning Nanodegree program. It is based on a Unity environment. The solution described in this repository is based on DDPG (Deep Deterministic Policy Gradient) architecture with a multi-agent approach. The agents share in this case the replay buffer and experiences.

The foundation for the solution was provided in the Udacity repository for the Deep Reinforcement Learning Nanodegree [Udacity Deep Reinforcement Learning Nanodegree](https://github.com/udacity/deep-reinforcement-learning/tree/master/p3_collab-compet)


You can find the detailled information on the exercise [here](https://github.com/udacity/deep-reinforcement-learning/blob/master/p3_collab-compet/README.md).

Find details on the Unity Reacher evnironment [here.](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#tennis)

## The task

The environment represents a two-player (agents) game where agents control rackets to bounce ball over a net. The goal for the agnets is to bounce ball between one another while not dropping or sending ball out of bounds.This environment contains two agent linked to a single Brain named TennisBrain. After training you can attach another Brain named MyBrain to one of the agent to play against your trained model.


The observation space consists of 24 variables corresponding corresponding to position and velocity of ball and racket. The vector action space is of size 2, corresponding to movement toward net or away from net, and jumping. If an agent hits the ball over the net, it receives a reward of +0.1. If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01. Thus, the goal of each agent is to keep the ball in play.

To solve the task (episodic), the agents must get a combined mean score of +0.5 over 100 consecutive episodes.

Aproach:

* After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 20 (potentially different) scores. We then take the average of these 20 scores.
* This yields an average score for each episode (where the average is over all 20 agents).

## Prerequisites

In order to run the code in this repository, it is required to follow the instructions as porvided in the Udacity Deep Reinforcment Learning Nanodegree repository. In order to install all required dependencies, please follow the instructions provided [here](https://github.com/udacity/deep-reinforcement-learning#dependencies).


Unity provides a prebuild simulator for multiple plattforms of the banana navigation environment. It is required to be installed and an environment need to be up and running to train and run the agent in scope of the exercise. Instructions on how to obtain it can be found in the 'Getting started' section in the following [README file](https://github.com/udacity/deep-reinforcement-learning/blob/master/p3_collab-compet/README.md)


## Instructions

1. Download the environment that matches your environment (I used the AWS setup for best perfromance). See Udacity's instruction on obtaining the right environment [here.](https://github.com/udacity/deep-reinforcement-learning/blob/master/p3_collab-compet/README.md)
2. Place the file in your copy of the [DRLND GitHub repository](https://github.com/udacity/deep-reinforcement-learning), in the p3_collab-compet/ folder, and unzip (or decompress) the file.
3. Copy the files model.py and agent.py as well as the Tennis.ipynb into the same folder. Replace Udacity's version of the Tennis.ipynb file with the version from this repo.

Run the notebook file Tennis.ipynb in this repository to further setup the notebook according to your environment, to train the agent, and to run the agent. The solution is setup to support GPU usage for training and inference. For a good performance running on GPU is highly recommended.

The training will generate the file checkpoint_actor.pth and checkpoint_critic.pth with the learned model weights. You can use this to simulate how your trained agent is behaving in the Unity environment.
