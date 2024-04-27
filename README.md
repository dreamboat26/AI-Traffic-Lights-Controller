# AI-Traffic-Lights-Controller

## Problem Statement 
The project uses reinforcement learning and genetic algorithms to improve traffic flow and reduce vehicle waiting times in a single-lane two-way junction simulator by coordinating traffic signal schedules. 

## What problem are you going to solve?
We aim to design an AI traffic lights controller to optimize and ensure better traffic flow using optimal light switching behavior.

## How are you going to solve it?
We will use two approaches: reinforcement learning and search.

## Why do you think that your approach is the right one?
Given a rush-hour traffic stream, the main goal of the AI traffic lights controller is to let all the cars pass as quickly as possible while avoiding collisions. With reinforcement learning, the agent can be rewarded and penalized based on predetermined rules, such as priority of passage for emergency vehicles, making it learn to solve the problem. With search, the agent can be pointed using heuristics toward the final state of no traffic. These two approaches allow the AI controller to calculate the optimal switching behavior for the traffic lights to shorten waiting times at junctions and reduce journey times.

## How are you going to test your results?
Using a traffic flow simulator, we will measure the average waiting and journey times and compare them at different stages of the learning process.

## Installation

git clone https://github.com/dreamboat26/AI-Traffic-Lights-Controller.git
cd AI-Traffic-Lights-Controller
pip install -r requirements.txt

## Usage

python main.py -m [method] -e [number of episodes] -r
 - m or --method: specifies which method to use for the traffic light controller. The available methods are 'fc', 'lqf', 'qlearning', and 'search'.
 - -e or --episodes: specifies the number of evaluation episodes to run.
 - -r or --render: optional flag - displays the simulation window if included.
 
 For example, this will run the default cycle method for 10 episodes and display the simulation window:
 
 python main.py -m fc -e 10 -r

## Possible Improvements
- We can tweak several hyper-parameters to change the results - all the Q-Learning parameters (exploration threshold, learning rate, discount rate) and the amount of time the agent waits between actions.
- We can change the representation of the state space and the reward function.
- For the reward function, instead of using the change in inbound vehicles, we can use throughput, wait time, vehicle speed, or any combination of those.
- To properly train an agent, it needs to see all the possible combinations of state-action several times, so the number of training episodes required will be in the hundreds of thousands - this requires more computational resources than our state space implementation.








