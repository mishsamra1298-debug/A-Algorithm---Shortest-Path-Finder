# A* Algorithm---Shortest-Path-Finder
This project demonstrates the A* algorithm to find the shortest path in a grid by combining cost and heuristic functions. It allows users to visualize path finding in different scenarios.

# Concepts Covered
Informed Search: A* uses a heuristic function h(n) to guide the search process.
Heuristics: Manhattan Distance is used, which is admissible and consistent.
Graph Traversal: The algorithm performs node expansion using open and closed lists.
Optimality: A* guarantees the shortest path when an admissible heuristic is used.
Problem Formulation: It includes state space, actions, goal test, and path cost.

A command-line implementation of the A* (A-Star) search algorithm — one of the most
widely used pathfinding algorithms in Artificial Intelligence. This project demonstrates how
A* efficiently finds the shortest path on a 2D grid with obstacles, using a heuristic function
(Manhattan Distance) to guide the search.

# What is A*?
A* is an informed search algorithm that combines:
g(n) — the actual cost from the start node to node n
h(n) — a heuristic estimate of the cost from n to the goal
f(n) = g(n) + h(n) — the total estimated cost
By always expanding the node with the lowest f(n) , A* guarantees the shortest path while
exploring fewer nodes than uninformed algorithms like BFS and DFS.

# Features :-
 A* pathfinding on a 2D grid
 Manhattan Distance heuristic
 Coloured terminal visualisation (path, walls, explored nodes)
 3 built-in scenarios (Simple, Maze, No-path)
 Custom grid builder (add walls interactively)
 Performance stats — path length, nodes explored, time taken
 Pure Python — no external dependencies

# Project Structure
astar_project/
|--- astar.py        # Main program (algorithm + CLI)
└--- README.md       # This file
|___Screenshots      #Output File

# Requirements :-
Python verion 3.7 or higher
Dependencies - None(standard library only)
Operating Structure - Windows/macOS/Linux

# How to Use :-
When you run the program, you will see a menu:
--- Select a scenario ---
  [1] Simple 8x8
  [2] Maze 10x10
  [3] No path possible
  [4] Custom grid
  [5] Quit

# Option 1 / 2 / 3 — Preset grids
Select a number and press Enter. The initial grid is shown, then press Enter again to run the
algorithm.

# Option 4 — Custom grid
1. Enter grid size (rows and columns, between 3 and 15)
2. Enter wall positions one by one as row,col (e.g. 2,3 )
3. Type done when walls are placed
4. Enter start and goal positions

# Reading the output
'S' symbol represents Start Position.
'G' symbol represents Goal Position.
'*' symbol represents Shortest Path.
'██' symbol represents Wall (obstacle).
'·'symbol represents node explored by A*.

# Sample output
--- Result ---
   +---+---+---+---+---+---+---+---+
 0 | S | * | * | * |   |   |   |   |
   +---+---+---+---+---+---+---+---+
 1 |   |███|███|███| * |   |   |   |
   +---+---+---+---+---+---+---+---+
...
✔  Path found!
   Path length    : 15 steps
   Nodes explored : 23
   Time taken     : 0.412 ms

# Algorithm Walkthrough
1. Add the start node to the open list with f = h(start, goal)
2. While the open list is not empty:
      Pop the node with the lowest f value
      If it is the goal, reconstruct and return the path
      Add it to the closed set
      For each valid neighbour:
          Compute g , h , f
          Add to open list if not already visited with a better cost
3. If the open list empties with no goal found → no path exists
  
