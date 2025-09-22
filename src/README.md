# graphs_AustynGriegoMSU

A Python library that implements Dijkstra's shortest path algorithm for finding shortest paths in weighted graphs.

## 🚀 Features

- **Dijkstra's Algorithm**: Efficient implementation of Dijkstra's shortest path algorithm
- **Custom Heap Implementation**: Includes a complete heap queue (priority queue) implementation
- **Path Reconstruction**: Returns both shortest distances and actual paths
- **Graph File Support**: Read graphs from formatted text files
- **Easy to Use**: Simple API for quick integration into your projects

## 📦 Installation

Install from PyPI:

```bash
pip install graphs-AustynGriegoMSU
```

## 🔧 Usage

### Basic Usage

```python
from graphs_AustynGriegoMSU import sp

# Define a graph as an adjacency dictionary
# Format: {source_node: {destination_node: weight, ...}, ...}
graph = {
    0: {1: 4, 2: 2},
    1: {2: 1, 3: 5},
    2: {3: 8, 4: 10},
    3: {4: 2},
    4: {}
}

# Find shortest paths from source node 0
distances, paths = sp.dijkstra(graph, source=0)

print("Shortest distances from node 0:")
print(distances)  # [0, 4, 2, 9, 11]

print("Shortest paths:")
for destination in paths:
    print(f"Path to node {destination}: {paths[destination]}")
```

### Using with Graph Files

The package includes a test script that can read graphs from text files:

```python
# File format: 
# First line: number of nodes
# Following lines: source destination weight

# Example graph.txt:
# 5
# 0 1 4
# 0 2 2
# 1 2 1
# 1 3 5
# 2 3 8
# 2 4 10
# 3 4 2

# Run the test script
python test.py graph.txt
```

### Custom Heap Operations

The package also provides a complete heap implementation:

```python
from graphs_AustynGriegoMSU import heapq

# Create and use a heap
heap = []
heapq.heappush(heap, 3)
heapq.heappush(heap, 1)
heapq.heappush(heap, 4)

smallest = heapq.heappop(heap)  # Returns 1
print(f"Smallest element: {smallest}")
```

## 🧮 Algorithm Details

### Dijkstra's Algorithm

The implementation uses Dijkstra's algorithm to find shortest paths from a source node to all other nodes in a weighted graph. 

**Time Complexity**: O((V + E) log V) where V is vertices and E is edges  
**Space Complexity**: O(V)

**Key Features**:
- Handles weighted directed graphs
- Returns both distances and path reconstruction
- Uses a min-heap for efficient next-node selection
- Supports graphs with any number of nodes

### Input Format

The graph should be represented as a dictionary where:
- Keys are source nodes (integers)
- Values are dictionaries mapping destination nodes to edge weights

```python
graph = {
    0: {1: 10, 2: 3},     # Node 0 connects to node 1 (weight 10) and node 2 (weight 3)
    1: {3: 2},            # Node 1 connects to node 3 (weight 2)
    2: {1: 4, 3: 8},      # Node 2 connects to node 1 (weight 4) and node 3 (weight 8)
    3: {}                 # Node 3 has no outgoing edges
}
```

### Output Format

The `dijkstra()` function returns a tuple containing:

1. **Distances**: A list where `distances[i]` is the shortest distance from source to node `i`
2. **Paths**: A dictionary where `paths[i]` is the shortest path from source to node `i`

## 📚 API Reference

### `sp.dijkstra(graph, source)`

Finds shortest paths from a source node to all other nodes.

**Parameters**:
- `graph` (dict): Graph represented as adjacency dictionary
- `source` (int): Source node index

**Returns**:
- `distances` (list): Shortest distances from source to each node
- `paths` (dict): Shortest paths from source to each node

**Example**:
```python
distances, paths = sp.dijkstra(graph, 0)
```

## 🛠️ Development

### Requirements

- Python >= 3.7
- No external dependencies

### Testing

Run the included test script:

```bash
python src/test.py path/to/your/graph/file.txt
```

### Graph File Format

Create a text file with your graph data:

```
5          # Number of nodes
0 1 4      # Edge from node 0 to node 1 with weight 4
0 2 2      # Edge from node 0 to node 2 with weight 2
1 2 1      # Edge from node 1 to node 2 with weight 1
...
```

## 📄 License

This project is licensed under the MIT License.

## 👨‍💻 Author

**Austyn Griego**  
Email: agriego4@msudenver.edu  
GitHub: [AustynGriegoMSU](https://github.com/AustynGriegoMSU)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📈 Version History

- **0.0.2**: Current version with Dijkstra's algorithm implementation
- **0.0.1**: Initial release

## 🔗 Links

- [GitHub Repository](https://github.com/AustynGriegoMSU/graphs_AustynGriegoMSU)
- [PyPI Package](https://pypi.org/project/graphs-AustynGriegoMSU/)

---

*This package was created as part of a Python packaging exercise and demonstrates graph algorithms implementation.*