It's just an array or linked list with one special rule which is data can only be inserted and deleted from one end of stack and of course size is dynamic

### Initialization 
	Stack stack = new Stack<data-type>()

### Insertion
	stack.push(value);

### Deletion
	stack.pop(); //return value optional

### Top element view
	stack.peek();

### Check size
	stack.size();

### Check if empty
	stack.isEmpty(); // return boolean

### Search
	stack.search(element); //return true if found