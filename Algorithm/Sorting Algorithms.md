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
- Heap Sort - learn when you have time or preparing for hardware focused interview
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
		// flag is used so that if after any pass nothing changes
		// meaning array becomes sorted so we exit early
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

##### Usage
Used as a sub routine inside hybrid sorting algorithm like Tim sort cause it works better in nearly sorted arrays.

### Merge Sort
recursively dividing the arrays in half and sorting both halves and merging back the sorted array.

```
void sort(int[] arr){
	// cause we are going to do things recursively
	int l=0, r=arr.length-1;
	mergeSort(arr, l, r);
}
void mergeSort(int[] arr, int l, int r){
	if(l<r){
		int mid = l+(r-l)/2;
		// dividing into left
		mergeSort(arr, l, mid);
		// dividing into right
		mergeSort(arr, mid+1, r);
		// merging
		merge(arr, l, mid, r);
	}
}
void merge(int[] arr, int l, int m, int r){
	int n1 = m-l+1;
	int n2 = r-m;

	// creating new arrays to store the halves
	int[] left = new int[n1];
	int[] right = new int[n2];

	for(int i=0; i<n1; i++){
		left[i] = arr[l+i];
	}
	for(int i=0; i<n2; i++){
		right[i] = arr[m+i+1];
	}

	int i=0, j=0;
	int k=l;

	// we keep merging based on priority
	while(i<n1 && j<n2){
		if(left[i] < right[j]){
			arr[k] = left[i++];
		}
		else{
			arr[k] = right[j++];
		}
		k++;
	}

	// merging the remains
	while(i<n1){
		arr[k++] = left[i++];
	}
	while(j<n2){
		arr[k++] = right[j++];
	}
}
```

##### Usage
used in Collections.sort() cause the TC in every case is O(n log(n)). best for parallel and external sorting

### Quick Sort
recursively sorting based on a pivot element (user defined position). Putting all the smaller elements on to the left side of the pivot and greater on the right.

```
void sort(int[] arr){
	int l=0, r=arr.length-1;
	quickSort(arr, l, r);
}

void quickSort(int[] arr, int l, int r){
	if(l<r){
		int pi = partition(arr, l, r);
		quickSort(arr, l, pi);
		quickSort(arr, pi+1, r);
	}
}

int partition(int[] arr, int l, int r){
	int pivot = arr[r] // or arr[l] (not this cause worst case when the array is already sorted) or arr[(l+r)/2] (optimal)
	int i = l-i;

	for(int j=l; j<r; j++){
		if(arr[j] < pivot){
			i++;
			swap(arr, i, j);
		}
	}
	swap(arr, i+1, r);
	return i+1;
}
```

##### usage
best for big dataset cause needs less memory