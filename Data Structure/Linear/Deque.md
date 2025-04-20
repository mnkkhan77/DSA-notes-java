It's just an **array or linked list** with one special rule which is data can be **inserted and deleted from both ends**, and of course, the size is dynamic.

**Deque is an interface**, meaning we have to implement it using either of [[LinkedList]], ArrayDeque, or ConcurrentLinkedDeque (for thread-safe operations)

### Initialization
`Deque<Integer> dq = new LinkedList<>(); 
`Deque<Integer> dq = new ArrayDeque<>(); // 90% time this one is used`

### Types
- ArrayDeque - resizable array implementation of deque  
    **usage** - faster than LinkedList in most cases for stack/queue operations
    
- LinkedList - doubly-linked list implementation of deque  
    **usage** - when frequent insertions/deletions at both ends are needed
    
- ConcurrentLinkedDeque - thread-safe implementation  
    **usage** - for concurrent use in multithreaded applications
    
### Insertion
`dq.addFirst(element); // throws error if capacity is exceeded
`dq.addLast(element); // throws error if capacity is exceeded` `dq.offerFirst(element); // returns false if capacity is exceeded` `dq.offerLast(element); // returns false if capacity is exceeded`

### Deletion
`dq.removeFirst(); // throws error if deque is empty
`dq.removeLast(); // throws error if deque is empty
`dq.pollFirst(); // returns null if deque is empty
`dq.pollLast(); // returns null if deque is empty`

### Front/Rear element viewing
`dq.peekFirst(); // returns null if deque is empty
`dq.peekLast(); // returns null if deque is empty
`dq.getFirst(); // throws error if deque is empty
`dq.getLast(); // throws error if deque is empty`