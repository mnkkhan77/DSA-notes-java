Rearranging elements in a certain order, usually in increasing or decreasing order.

### Some important terms 
- Stable sorting - maintaining the original order of elements after sorting
- Unstable sorting - Doesn't maintain order
- Comparison Based sorting
- Non Comparison Based sorting
- Hybrid sorting - using both comparisons and non comparison

### Types of sorting
#### comparison based
- Selection Sort
- Bubble Sort
- Insertion Sort
- Merge Sort
- Quick Sort
- Heap Sort
- Cycle Sort
- 3-way Merge Sort

#### non comparison based
 - Counting Sort
 - Radix Sort
 - Bucket Sort
 - TimSort
 - Comb Sort
 - Pigeonhole Sort

### Selection sort
sequentially selecting the smallest/largest element and swapping with the unsorted

```
public static void selectionSort(int[] arr){
	int n = arr.length;
	for(int i=0; i<n; i++){
		int min_index = i;
		for(int j=i+1; j<n; j++){
			// searching for the smallest element in the range
			// and saving that index
			if(arr[j] < arr[min_index]){
				min_index = j;
			}
		}
		// now will swap those elements
		int temp = arr[i];
		arr[i] = arr[min_index];
		arr[min_index] = temp;
	}
}
```

##### Usage
- used when resources provided are low
- where system predictability is important cause it is consistent with O(n^2) TC.
- usage in heaps

### Bubble sort
sequentially and repeatedly swapping elements to sort the elements

```
void bubbleSort(int[] arr){
	for(int i=0; i<n; i++){
		boolean flag = false;
		for(int j=i; j<n-1; j++){
			if(arr[j] > arr[j+1]){
				flag = true;
				swap(arr[j], arr[j+1]);
			}
		}
		if(flag) return;
	}
}
```

##### Usage
Performs better when the input list is already mostly sorted.

### Insertion sort
sequentially sorting the elements like sorting in a sorted and unsorted deck of cards

```
void insertionSort(int[] arr){
	// since one element will always be there in any sorted array
	for(int i=1; i<n; i++){
		// the element which we are going to sort
		int key = arr[i];

		// we will just shift the elements to the right untill we find the correct spot
		int j=i-1;

		while(j >= 0 && arr[j] > key){
			// the shifting
			arr[j+1] = arr[j];
			j = j-1;
		}
		// marking the value
		arr[j+1] = key;
	}
}
```