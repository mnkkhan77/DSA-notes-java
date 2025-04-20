Have same type of data but not in contiguous manner

### Declaration

`// Definition of a Node in a singly linked list`
`public class Node {`
    `int data;`
    `Node next;`

    // Constructor to initialize the node with data
    public Node(int data)
    {
        this.data = data;
        this.next = null;
    }
}

### Types
- Singly LL
- Doubly LL - there's next as well as previous pointer
- Circular LL - last node points to the head node

### Usage
where lots of addition, removal operations are going to be done, like in stack, queue etc

### Traversal
	`void traverse(Node head) {
		`Node temp = new Node(0);`
		`while(temp != null) {`
			`Syste.out.print(temp.data+" ");`
			`temp = temp.next;`
		`}`
	`}`

### Deletion of a node
	#### when the head is given and node is given
		`void delete(Node head, Node node){`
			`while(head.next != node {`
				`head = head.next;`
			`}`
			`head.next = head.next.next`;
		`}`

	#### when only node to be deleted is given
		`void delete(Node node){`
			// cannot delete last node with this method`
			`if(node.next == null) return;`
			`else{`
				`node.data = node.next.data;`
				`node.next = node.next.next;`
			`}`
		`}`

### Insertion of a node
	#### Insertion at head
		`Node insert(Node head, Node node){`
			`node.next = head;`
			`head = node;`
		`}`

	#### Insertion at anywhere
		`Node insert(Node head, int value, int position){`
			`Node temp = head;`
			`for(int i=0; i<position-1; i++){`
				`temp = temp.next;`
			`}`
			`Node node = new Node(value);`
			`node.next = temp.next;`
			`temp.next = node;`
		`}`

### Reversal of Linked List
	`Node reverse(Node head){`
		`Node prev = null;`
		`while(head != null){`
			`Node next = head.next;`
			`head.next = prev;`
			`prev = head;`
			`head = next;`
		`}`
		`return prev;`
	`}`

