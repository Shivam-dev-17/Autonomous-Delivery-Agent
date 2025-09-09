# Autonomous-Delivery-Agent
Project Overview
This project implements an **autonomous delivery agent** that navigates a 2D grid city to deliver packages efficiently.  
It was developed as part of **CSA2001 – Fundamentals of AI and ML (Project-Based Learning)
The agent can:
Model the environment (static obstacles, varying terrain costs, dynamic moving
obstacles).
Be rational: choose actions that maximize delivery efficiency under constraints
(time, fuel).
Implement uninformed (BFS/Uniform-cost), informed (A* with admissible
heuristic), and a local search replanning strategy (e.g., hill-climbing with random
restarts or simulated annealing) to handle dynamic obstacles / changing traffic
costs.
Compare algorithms experimentally on several map instances and report results
(path cost, nodes expanded, time).
Provide analysis describing when each method performs better and why.
Repository Structure:
Autonomous-Delivery-Agent/
├── delivery_agent.py 
├── maps/
│ ├── small.txt
│ ├── medium.txt
│ ├── large.txt
│ └── dynamic.txt
│
├── experiments/
│ ├── results.csv
│ └── plots.png
│
├── screenshots/
│ └── astar_dynamic.png
│
├── recordings/
│ └── demo.mp4
│
├── tests/
│ └── test_search.py
│
├── README.md
└── report.pdf

## Environment Model
- The **grid** is represented as a text file.
- Each cell has an **integer cost ≥ 1**.
- **Static obstacles**: `#`
- **Start/Goal**: `S`, `G`
- Example:
1 1 1 G
1 # 1 1
S 1 1 1

**Dynamic obstacles** can be defined after a blank line:
1 1 1 1 G
S 1 # 1 1

Dynamic schedule (time row col)
1 0 2
2 1 2

## Algorithms Implemented
1. **BFS (Breadth-First Search)**  
 - Finds shortest path in terms of steps.  
 - Ignores terrain cost.  

2. **UCS (Uniform-Cost Search)**  
 - Considers terrain cost.  
 - Expands cheapest path first.  

3. **A* Search**  
 - Uses **Manhattan distance heuristic**.  
 - Optimal and efficient on large maps.  

4. **Local Search Replanning (Hill-Climbing with Random Restarts)**  
 - Handles **dynamic obstacles**.  
 - Replans when obstacles block the current path.

Run with specific algorithm
```bash
python delivery_agent.py --algo bfs --map maps/small.txt
python delivery_agent.py --algo ucs --map maps/medium.txt
python delivery_agent.py --algo astar --map maps/large.txt
python delivery_agent.py --algo local --map maps/dynamic.txt --dynamic

Run demo (all algorithms on all maps)
python delivery_agent.py --demo
