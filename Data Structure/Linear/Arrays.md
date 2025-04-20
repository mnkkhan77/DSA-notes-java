Have same type of data in contagious manner like int, char, boolean etc

### Operations - 

- Traversing
- Insertion
- Deletion
- Searching
- Sorting

### Declaration
`int[] array = new int[size];`

### Traversal
`for(int i=0; i<size; i++){`
	`array[i];`
	`System.out.println(array[i]);`
`}`

### Insertion
`array[position] = value`

### Deletion
`array[position] = 0`

### Sorting
	`Arrays.sort(array)` ascending
	`Arrays.sort(a, Collections.reverseOrder());` descending

### Searching
#### - Linear Search
	`for(int i=initial position; i<final position; i++){
		`if(arr[i] == element){`
			`return true;`
		`}`
	`}`
	`return false;`
#### - Binary Search (Works in some kind of sorted values typically arrays)
	`Arrays.sort(array)`
	`Arrays.binarySearch(array, element)`
	`Arrays.binarySearch(array, from_index, to_index, element)`