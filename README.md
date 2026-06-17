# 🤖 Multi-Agent Foraging using Q-Learning

## Overview

This project implements a Multi-Agent Reinforcement Learning (MARL) system where autonomous Forager Agents learn how to efficiently collect renewable Food Resources in a dynamic grid-based environment.

The objective is to investigate how Q-Learning enables agents to improve their resource collection strategies over time while interacting with obstacles, competing agents, and a continuously changing environment.

The project evaluates both single-agent and multi-agent learning scenarios and compares independent versus shared learning policies.

---

## Objectives

* Implement Q-Learning for autonomous Forager Agents.
* Develop a dynamic Grid World environment.
* Enable agents to learn optimal resource collection strategies.
* Analyze learning performance over time.
* Compare independent and shared Q-Table approaches.
* Study competition and implicit cooperation among agents.

---

## Environment Configuration

### Grid Environment

* Grid Size: 10 × 10
* Renewable Food Resources: 10
* Obstacles: 5+
* Agent Actions:

  * Move Up
  * Move Down
  * Move Left
  * Move Right

### Environment Rules

* Agents cannot move outside grid boundaries.
* Agents cannot pass through obstacles.
* Food resources respawn at random empty locations after collection.
* Agent collisions are penalized.

---

## Q-Learning Implementation

### State Representation

Each state represents the current environment information used by the agent to make decisions.

### Action Space

```text
0 → Up
1 → Down
2 → Left
3 → Right
```

### Reward Function

```text
+10  Collect Food Resource
-1   Movement without collecting food
-5   Collision with another agent
```

### Learning Parameters

* Learning Rate (α)
* Discount Factor (γ)
* Exploration Rate (ε)
* Epsilon Decay Strategy

### Action Selection

The epsilon-greedy policy is used to balance:

* Exploration (random actions)
* Exploitation (best-known actions)

### Q-Value Update

```text
Q(s,a) = Q(s,a) + α [ r + γ max(Q(s',a')) − Q(s,a) ]
```

---

## Experiments

### Single-Agent Simulation

Experiments were conducted using:

* 200 Episodes
* 1000 Episodes

Metrics collected:

* Total Reward per Episode
* Food Resources Collected
* Episode Length
* Exploration vs Exploitation Counts

### Multi-Agent Simulation

Three Forager Agents learn simultaneously within the same environment.

Two learning strategies were evaluated:

#### Independent Q-Tables

Each agent maintains its own policy and experience.

#### Shared Q-Table

Agents learn from a common policy and shared experience.

Metrics collected:

* Agent Position
* Total Reward
* Resources Collected
* Collision Count

---

## Results and Analysis

The project investigates:

* Learning efficiency over time
* Resource collection performance
* Impact of exploration and exploitation
* Competition for limited resources
* Agent collision behavior
* Independent versus shared learning performance

Learning curves are generated for:

* Total Reward per Episode
* Resources Collected per Episode

Comparative analysis highlights the effect of shared knowledge on overall system performance.

---

## Technologies Used

* Python
* Jupyter Notebook
* NumPy
* Pandas
* Matplotlib
* CSV Data Logging

---

## Project Structure

```text
Multi-Agent-Foraging-QLearning/
│
├── data/
│   ├── single_agent_results.csv
│   ├── multi_agent_results.csv
│
├── figures/
│   ├── reward_curve.png
│   ├── resources_curve.png
│
├── notebooks/
│   └── MultiAgent_Foraging.ipynb
│
├── report/
│   └── Report.pdf
│
└── README.md
```

---

## Key Learning Outcomes

* Reinforcement Learning Fundamentals
* Q-Learning Algorithm
* Multi-Agent Systems
* Exploration vs Exploitation Trade-Off
* Grid-Based Agent Navigation
* Cooperative and Competitive Agent Behavior
* Performance Evaluation and Visualization

---

## Future Improvements

* Deep Q-Networks (DQN)
* Larger Grid Environments
* Communication Between Agents
* Advanced Reward Shaping
* Cooperative Multi-Agent Reinforcement Learning (MARL)

---

## Author

**Merna Ayman**

Artificial Intelligence Student

