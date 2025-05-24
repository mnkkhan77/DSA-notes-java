we define a range/window where we do the operation, the range is defined using one pointers from left and another from right and it moves as per requirement generally from left to right maintaining the k size of the window.

### Types
- fixed size - sliding one step at a time 
- variable size - increasing by sliding right pointer and decreasing by sliding left as per requirement.

### Problem Identification
- These problems generally require **Finding Maximum/Minimum Subarray**, Substrings which satisfy some specific condition.
- The **size of** the subarray or substring **K** will be given in some of the problems.
- These problems can easily be solved in O($N^2$) time complexity using nested loops, using sliding window we can solve these in **O(n)** Time Complexity.
- **Required Time Complexity:** O(N) or O(Nlog(N))
- **Constraints:** N <= 106 , If N is the size of the Array/String.

##### Example
```
	// Max sum of size K
		int max_sum = 0;
        for (int i = 0; i < k; i++)
            max_sum += arr[i];

        // removing left element
        // adding right element
        // maintaing the size K
        int window_sum = max_sum;
        for (int i = k; i < n; i++) {
            window_sum += arr[i] - arr[i - k];
            max_sum = Math.max(max_sum, window_sum);
        }
```
