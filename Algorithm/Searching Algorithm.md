There are few algorithms for searching, yes, more than 2

## Types of Searching
- Linear
- **Binary** - this one is important, you have to learn this any how specially BS on searching space
- Ternary
- Jump Search
- Interpolation
- Fibonacci 
- Exponential 

### Linear Searching
- Only used when the data is unsorted

### Binary Search
- Used when the elements are in sorted order
- TC - $O(log2N)$

```
int binarySearch(int[] arr, int key){
	int left = 0, right = arr.length-1;
	while(left <= right){
		// why we did like this?
		// cause if the right value is extreme
		// then it will cause overflow in the calculation
		int mid = left + (right-left)/2; 
		if(arr[mid] == key) return mid;
		// cause it is sorted
		// so there is no point in searching in the left part
		// if it is guaranteed that the answer doesn't lies there
		else if(arr[mid] < key){
			left = mid+1;
		}
		// same as above but for the right side
		else if(arr[mid] > key){
			right = mid-1;
		}
		return -1;
	}
}
```

### Ternary Search
- Used in sorted elements
- TC - O($log3N$) 

```
int ternarySearch(int[] arr, int key){
	int left = 0, right = arr.length-1;
	while(left <= right){
		int mid1 = left + (right-left)/3;
		int mid2 = right - (right-left)/3;

		if(arr[mid1] == key) return mid1;
		if(arr[mid2] == key) return mid2;

		if(key < arr[mid1]){
			right = mid1-1;
		}
		else if(arr[mid2] < key){
			left = mid2+1;
		}
		else{
			left = mid1+1;
			right = mid2-1;
		}
	}
	return -1;
}
```

### Jump Search
just an optimization on linear search and works when data is sorted
	we just pick a window which we are going to skip every time if it doesn't contains the answer and if we cross over the answer then we come back one jump and then do linear search on that window. **TC- $O(√n)$**

### Interpolation Search
works when the data is uniformly sorted and distributed.
	the only difference between BS and IS is the picking of partition point. In IS point is calculated based on if the key lies closer to left or right everything else is same as BS

```
pos = lo+ (((hi - lo) / (arr[hi] - arr[lo])) * (key - arr[lo]));
	upper part is (key-arr[lo]) * (hi-lo)
	bottom part is arr[hi] - arr[lo]
	sum part is lo
```

### Fibonacci Search
used when the elements are very large and can't be stored in RAM or cpu cache.
	same as BS just the partition point is the same or greater than Fibonacci elements

### Exponential Search
used when the search space size is undefined so we basically start with $i = 2$ and increase the size by $i*2(exponential)$ untill the searchable element is in the search space

```
while (i < n && arr.get(i) < x)
        i *= 2;
```

