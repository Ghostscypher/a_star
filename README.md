# A* Pathfinding Algorithm

## Introduction

This is an implementation of the A* pathfinding algorithm. The A* pathfinding algorithm is used to find the shortest path between two points. The A* pathfinding algorithm is a combination of the Dijkstra's algorithm and the Greedy Best-First-Search algorithm. The A* pathfinding algorithm uses a heuristic to find the shortest path between two points. The A* pathfinding algorithm uses a priority queue to find the shortest path between two points.

## Installation

To run the simulation, simply clone the repository and open the `index.html` file in your browser. Alternatively, you can visit the [GitHub Pages](https://ghostscypher.github.io/a_star/src/index.html) for this repository.

## Explanation

### A* pathfinding algorithm

The A* pathfinding algorithm is a combination of the Dijkstra's algorithm and the Greedy Best-First-Search algorithm. The A* pathfinding algorithm uses a heuristic to find the shortest path between two points. The A* pathfinding algorithm uses a priority queue to find the shortest path between two points.

### Heuristic

The heuristic is used to estimate the distance between two points. The heuristic is used to estimate the distance between the current node and the target node. The heuristic is used to estimate the distance between the current node and the start node. The heuristic is used to estimate the distance between the current node and the end node. The heuristic is used to estimate the distance between the current node and the goal node.

### Pseudocode

Taken from [Wikipedia](https://en.wikipedia.org/wiki/A*_search_algorithm#Pseudocode)

```java
function A*(start, goal)
    // The set of nodes already evaluated
    closedSet := {}

    // The set of currently discovered nodes that are not evaluated yet.
    // Initially, only the start node is known.
    openSet := {start}

    // For each node, which node it can most efficiently be reached from.
    // If a node can be reached from many nodes, cameFrom will eventually contain the
    // most efficient previous step.
    cameFrom := an empty map

    // For each node, the cost of getting from the start node to that node.
    gScore := map with default value of Infinity

    // The cost of going from start to start is zero.
    gScore[start] := 0

    // For each node, the total cost of getting from the start node to the goal
    // by passing by that node. That value is partly known, partly heuristic.
    fScore := map with default value of Infinity

    // For the first node, that value is completely heuristic.
    fScore[start] := heuristic_cost_estimate(start, goal)

    while openSet is not empty
        // This operation can occur in O(1) time if openSet is a min-heap or a priority
        // queue
        current := the node in openSet having the lowest fScore[] value
        if current = goal
            return reconstruct_path(cameFrom, current)

        openSet.Remove(current)
        closedSet.Add(current)
        for each neighbor of current
            if neighbor in closedSet
                continue		// Ignore the neighbor which is already evaluated.

            // The distance from start to a neighbor
            tentative_gScore := gScore[current] + dist_between(current, neighbor)
            if neighbor not in openSet	// Discover a new node
                openSet.Add(neighbor)
            else if tentative_gScore >= gScore[neighbor]
                continue		// This is not a better path.

            // This path is the best until now. Record it!
            cameFrom[neighbor] := current
            gScore[neighbor] := tentative_gScore
            fScore[neighbor] := gScore[neighbor] + heuristic_cost_estimate(neighbor, goal)

    return failure
```

## Using the simulation

The simulation is very simple to use. The simulation will start automatically when the webpage is loaded.

1. The simulation can be reset by pressing the `r` key.
2. The simulation can be paused by pressing the `p` key.
3. When the simulation is paused, we enter into the select mode. In the select mode, we can select the start node, the end node. The start node is selected using the left mouse button. The end node is selected using the right mouse button.
4. The simulation can be resumed by pressing the `p` key. If we made any selection the simulation will start with the new selection. If we did not make any selection the simulation will resume with the previous selection.
5. To toggle the walls on or off, press the `w` key. Note that whenever the walls are toggled on or off, the simulation will be reset.

## Demo

<img src="https://ghostscypher.github.io/a_star/src/index.html" title="A*_search_algorithm" width="100%" height="500px">

## References

1. [A* search algorithm](https://en.wikipedia.org/wiki/A*_search_algorithm)
2. [P5 JS](https://p5js.org/)
3. [P5 JS Reference](https://p5js.org/reference/)
4. [P5 JS Examples](https://p5js.org/examples/)
5. [P5 JS Web Editor](https://editor.p5js.org/)
6. [Coding train - P5 JS Tutorials](https://www.youtube.com/user/shiffman/playlists?view=50&sort=dd&shelf_id=14)
7. [The Nature of Code](https://natureofcode.com/)
8. [The Coding Train](https://thecodingtrain.com/)
9. [The Coding Train - A* Pathfinding Algorithm](https://www.youtube.com/watch?v=aKYlikFAV4k)
10. [The Coding Train - A* Pathfinding Algorithm - Part 2](https://www.youtube.com/watch?v=JtiK0DOeI4A)
11. [The Coding Train - A* Pathfinding Algorithm - Part 3](https://www.youtube.com/watch?v=SmkYygyxw18)