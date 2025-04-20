Hierarchical structure that is used to represent and organize data in the form of parent child relationship.

### Usage 
- file system on a computer.
-  DOM model of an HTML page is also tree where we have html tag as root, head and body its children and these tags, then have their own children.

### Important terms
- Root Node - topmost node of a non empty tree
- Parent Node - Node above the child node, parent node have link to child node
- Child Node - Node below the parent node, there's no link from child to parent
- Leaf Node - Nodes which don't have any child
- Ancestor of a Node - Any top level node from which we can reach to current node
- Descendant Node - From current node we can reach to the descendant node
- Sibling - Nodes at same Parent
- Neighbor Node - Parent or Child nodes are neighbor
- Subtree - Any Node of the tree along with its descendant 

### Declaration
	public static class Node {
	    int data;
	    Node first_child;
	    Node second_child;
	    Node third_child;
	    .
	    .
	    .
	    Node nth_child;
    }

### Types
- Binary Tree - Node with maximum of 2 children
- Ternary Tree - Node with max of 3 children
- N-ary tree or Generic type - Any number of children example **trie**. Technically a Directed Acyclic Graph (DAG)

### Usage
- BST (Binary Search Tree) - sorted tree for efficient search. O(log(n))
- Heaps (priority queue)

### Types of Binary Tree
- Complete BT - tree is filled sequentially from top to left and left to right
- Full BT - All nodes with 0 or 2 children
- Degenerate BT - a linked list
- BST - a tree whose data is sorted in order of left, root and right nodes
	- AVL tree - self balancing, level difference is max 1. preferred for frequent search
	- Red Black tree - self balancing with additional attribute of color (red or black). maintains balance during insertion/deletion. preferred for frequent insertion/deletion operation.
	- Splay tree - self balancing. make most recently accessed or inserted element to the root of the tree by performing a sequence of tree rotations. doesn't guarantee balanced tree structure
- Perfect BT - have all 2 children and leaf at same level
- Balanced BT - difference between any level is maximum 1
- Segment Tree - used for storing intervals or segments. good for finding the sum, minimum, maximum, or other operations over a range of elements in an array.

#### We generally work on binary tree

### Property of Binary Tree
- max no. of nodes at level L is $2^L$ .
- max no. of nodes of height H in a BT is $2^H$ -1.
- with N nodes, min possible height will be $log2(N+1)$

### Complexity of BT
| Operation              | Time Complexity | Auxiliary Space |
|------------------------|------------------|------------------|
| In-Order Traversal     | O(n)             | O(n)             |
| Pre-Order Traversal    | O(n)             | O(n)             |
| Post-Order Traversal   | O(n)             | O(n)             |
| Insertion (Unbalanced) | O(n)             | O(n)             |
| Searching (Unbalanced) | O(n)             | O(n)             |
| Deletion (Unbalanced)  | O(n)             | O(n)             |

