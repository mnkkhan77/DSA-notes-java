It's just an array or linked list with one special rule which is data can only be **inserted from one end and deleted from another** and of course size is dynamic.

**queue is an interface** meaning we have to implement it using either of [[Linked List]] , PriorityQueue, ArrayDeque, ConcurrentLinkedQueue (for thread-safe operations)

### Initialization 
	Queue<Integer> q = new LinkedList<>();

### Types
- Deque (Double ended queue) - operations can be done from both end
	**usage** - to efficiently add/remove from both end, like in LRU, LFU cache
- Priority Queue (Heap) - where elements are processed based on their priority rather than insertion order like in hospital
	**usage** - to keep the elements sorted inside queue like for task scheduling or shortest/longest path
	**operation** - insertion and deletion is log(n) instead of O(1)
	
### Insertion
	q.add(element); // throws error if queue is full
	q.offer(element); // return false if queue is full, typically used in tree or graph dsa

### Deletion
	q.remove(); // throws error if queue is empty
	q.poll(); // return false if queue is empty, typically used in tree or graph dsa

### Front element viewing 
	q.peek(); // error if empty
	q.element(); // return false if empty