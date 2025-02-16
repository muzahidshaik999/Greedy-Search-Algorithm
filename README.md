# Greedy-Search-Algorithm
# Greedy Best-First Search Algorithm

This repository contains a Python implementation of the **Greedy Best-First Search Algorithm** to find a path from a start node to a goal node using heuristic values.

## 📌 Overview
The **Greedy Best-First Search** algorithm selects the next node based on the lowest heuristic value, aiming to reach the goal as quickly as possible. However, it does not guarantee the shortest path.

## 🚀 Features
- Implements **Greedy Best-First Search**.
- Uses a **graph representation** with predefined **heuristic values**.
- Finds a path to the goal using heuristic-based selection.
- Outputs the sequence of nodes visited.

## 📂 Project Structure
```
.
├── greedy_search.py    # Main script containing the algorithm
├── README.md           # Project documentation
```

## 📝 Algorithm Explanation
1. **Graph Representation**: The problem is represented as a dictionary where keys are nodes and values are lists of adjacent nodes.
2. **Heuristic Function**: Each node has an associated heuristic value representing an estimate of the cost to reach the goal.
3. **Search Process**:
   - Start from the initial node.
   - Select the child node with the **lowest heuristic value**.
   - Repeat until the goal is reached or no more moves are possible.

## 🖥️ Code Implementation
```python
# Define the graph
graph = {
    'S': ['A', 'B'],
    'A': ['C', 'D'],
    'B': ['E', 'F'],
    'C': [],
    'D': [],
    'E': ['H'],
    'F': ['I', 'G'],
    'G': [],
    'H': [],
    'I': []
}

# Define heuristic values
heuristic = {
    'S': 13, 'A': 12, 'B': 4, 'C': 7, 'D': 3, 'E': 8, 'F': 2, 'G': 0, 'H': 4, 'I': 9
}

def find_min_heuristic(node):
    if not graph[node]:  
        return None  

    min_node = graph[node][0]
    min_value = heuristic[min_node]

    for child in graph[node]:
        if heuristic[child] < min_value:
            min_value = heuristic[child]
            min_node = child
    
    return min_node  

def greedy(start, goal):
    while True:
        print(start, end=' ')
        
        if start == goal:
            print("\nGoal is Reached")
            return
        
        next_node = find_min_heuristic(start)
        
        if next_node is None:  
            break
        
        start = next_node  
    
    print("\nGoal is not reached")

greedy('S', 'G')
```

## 🛠️ Installation & Usage
1. **Clone the Repository**
```sh
git clone https://github.com/your-username/greedy-search.git
cd greedy-search
```

2. **Run the Script**
```sh
python greedy_search.py
```

## 🎯 Example Output
```
S B F G
Goal is Reached
```

## 📌 Limitations
- The algorithm does not backtrack if a wrong path is taken.
- It does not guarantee finding the shortest path.
- Can get stuck in loops if heuristics are not well-defined.



---
Happy Coding! 🚀

