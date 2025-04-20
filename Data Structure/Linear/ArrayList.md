Same as Arrays but dynamic in size

## Declaration
`ArrayList<Integer> list = new ArrayList<>(size); // size is optional` 

## Methods
### - Fetch
  `list.get(position)`
### - Add
	`list.add(item)`
	`list.add(item, position)`
### - Remove/Delete
	`list.remove(position)`
### - Searching
	`list.contains(element)` // return true if found
### - Sorting
	`Collections.sort(list)` in ascending
	`Collections.sort(list, Collections.reverseOrder())` in descending
	`list.sort(Collections.reverseOrder());`
