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
