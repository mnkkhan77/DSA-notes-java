It's just a **complete binary tree** implemented using **array** with one special rule:  
**the element with the highest (or lowest) priority is always at the front**, not the one inserted first.

**PriorityQueue is a class**, not an interface, and it uses a **min-heap** by default (smallest element at the top).

### Initialization

`PriorityQueue<Integer> pq = new PriorityQueue<>(); // min-heap (default)  PriorityQueue<Integer> pq = new PriorityQueue<>(Collections.reverseOrder()); // max-heap`  

### Types
- Min-Heap – smallest element has the highest priority  
    **usage** – Dijkstra’s, Prim’s, scheduling tasks, top-K problems
    
- Max-Heap – largest element has the highest priority  
    **usage** – leaderboard, largest K elements, median maintenance
    
- Custom Heap – using comparator to define custom order  
    **usage** – for custom objects like jobs, patients, etc.
    

### Insertion
`pq.add(element); // throws error if queue is full (rarely used)
`pq.offer(element); // returns false if queue is full`

### Deletion (removes the highest-priority element)
`pq.remove(); // throws error if queue is empty
`pq.poll(); // returns null if queue is empty`

### Peek (view the top-priority element)
`pq.peek(); // returns null if queue is empty
`pq.element(); // throws error if queue is empty`

### Notes
- Operations like insertion and deletion are **O(log n)**
- Heap is internally backed by an array and re-heapifies after every operation
- For custom objects:    
    `PriorityQueue<Node> pq = new PriorityQueue<>((a, b) -> a.cost - b.cost);`
    >This will sort on the basis of first element and in ascending order
    
    