Collection of nodes connected by edges. Denoted by G(V, E, W). V-vertex, E-edge, W-weight.

### Usage

- Social network analysis 
- Recommendation systems.
- Computer networks.

### Types of Graph

- Null graph - no edges
- **Trivial graph** - Single node
- Undirected Graph - When there is no direction between any nodes just edge. Like a two way road.
- Directed graph - When there is direction between edges and we can only travel from source to destination node and not the opposite. Like a one way road.
- Connected Graph - From one node we can visit any other node
- Disconnected Graph - Can't visit to all node from any node
- **Regular Graph** - when degree of every node is equal to K.
- Complete Graph - Each node is connected to every other node.
- Cyclic Graph - graph containing at least one cycle
- Directed Acyclic Graph - a directed graph not containing any cycle.
- Bipartite Graph - A graph in which vertex can be divided into two sets such that vertex in each set does not contain any edge between them.
- Weighted Graph - Edges have specified weight.

### Complexity of Graph
| Action           | Adjacency Matrix | Adjacency List | Edge List |
|------------------|------------------|----------------|-----------|
| Adding Edge      | O(1)             | O(1)           | O(1)      |
| Removing an edge | O(1)             | O(N)           | O(E)      |
| Initializing     | O(N*N)           | O(N)           | O(E)      |

### Representation of Graph

#### - Adjacency Matrix

graph is stored in **2D matrix** where row and column is edge between vertices and the entry/values shows weight.
			`int[][] mat` =  {{ 0, 5, 0, 0 },
                        { 10, 0, 4, 0 },
                        { 0, 12, 0, 3 },
                        { 0, 0, 1, 0 }};
    here it shows, there is a path between 1->2 whose weight is 10 and path between 2 -> 1 whose weight is 5 and so on.

Here's the **addEdge** method -
		`public static void addEdge(int[][] mat, int i, int j) {`
	        `mat[i][j] = 1;`
	        `mat[j][i] = 1; // Since the graph is undirected and if it was directed then this line would be excluded`
	    `}`

##### Best for:
- **Dense graphs** (lots of edges)
- When you want **fast edge lookups** (`O(1)` time)
- Graphs with **a small number of vertices**
##### Downsides:
- Uses `O(V^2)` space even if there are few edges
- Not ideal for sparse graphs

#### Adjacency List
Graph is stored in List of List where the inner list shows all the neighbors of the current node.

	`List<List<Integer>>`	   0: 1 2 
					   1: 0 2 
				       2: 0 1 3 
				       3: 2

Here's the addEdge method - 
		`public static void addEdge(List<List<Integer>> adj, int i, int j)`
		`{`
	        `adj.get(i).add(j);`
	        `adj.get(j).add(i); // Undirected`
	    `}`

##### Best for:
- **Sparse graphs** (few edges)
- More **space-efficient**: `O(V + E)`
- When you need to **iterate over neighbors** often.
##### Downsides:
- Slower edge lookups (`O(degree)` time)

#### Edge List
Graph is stored as a list of edges from source to destination.

	List<int[]>   (0 -> 1, weight: 4)
				(1 -> 2, weight: 5)
				(2 -> 3, weight: 2)
				
Here's the addEdge method -
		`public void addEdge(int src, int dest) {`
	        `edgeList.add(new Edge(src, dest));`
	    `}`

##### Best for:
- **Simple algorithms** like Kruskal’s (in MSTs)
- When you need to **sort edges**, or care more about edges than vertices
##### Downsides:
- Not good for fast access to neighbors or edge lookup