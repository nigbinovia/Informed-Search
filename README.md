# Informed-Search
This project demonstrates informed search using A* to solve the 8-puzzle problem. The solving process is divided into two parts: creating the puzzle and solving the puzzle.


## Code Development
In creating the puzzle, the `random_board.py` program was developed. It takes a seed number and a number of random moves as input, and applies those moves to the base (goal) state to generate a randomized board configuration. The result is printed in a 3x3 format.
```
0 1 2
3 4 5
6 7 8
```

In solving the puzzle, the `a-star.py` program was developed. It reads the board configuration from standard input and uses a specified heuristic to solve the puzzle using the A* search algorithm. A* combines the actual path cost and heuristic estimates to efficiently find the solution.


The `a-star.py` uses two core classes:

* The Node class represents a puzzle state, storing the board layout, tile positions, path cost (g), and parent node.
* The Explore class implements the A* search and supports multiple heuristics.


The algorithm uses a priority queue (open list) to expand nodes in order of increasing estimated cost f(n) = g(n) + h(n). It continues until the goal state is found or all nodes are explored. Upon finding a solution, the program prints:

```
Total nodes visited (V)

Maximum nodes in memory (N)

Solution depth (d)

Approximate effective branching factor (b), where N = b^d

The sequence of states from start to goal
```

## Heuristics Implemented
The program supports four heuristic options:
```
0: No Heuristic (h(n) = 0) – Equivalent to Uniform Cost Search

1: Misplaced Tiles – Counts the number of tiles not in the correct position

2: Manhattan Distance – Sums the vertical and horizontal distances of tiles to their goal positions

3: Manhattan Distance + Linear Conflicts – Enhances heuristic 2 by considering tiles in the same row/column that block each other’s path

```

