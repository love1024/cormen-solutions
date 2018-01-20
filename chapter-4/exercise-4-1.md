### `Exercise 4.1-1`
***
What does FIND-MAXIMUM-SUBARRAY return when all elements of A are negative?
### Answer.
When all elements are negative then the maximum subarray will return the single least negative element.  
### `Exercise 4.1-2`
***
Write pseudocode for the brute-force method of solving the maximum-subarray
problem. Your procedure should run in O(n^2) time.  
### Answer.

    int maximumSubarray(int A[],int n) {
        //To store maximum subarray sum and temporary sum
        int maxSum = 0,tempSum=0;
        
        //Consider each subarray possible and find the maximum sum
        for(int i=0;i<n;i++) {
            for(int j=i;j<n;j++) {
                tempSum += A[j];
                if(tempSum > maxSum) {
                    maxSum = tempSum;
                }
            }
            tempSum = 0;
        }
        return maxSum;
    }
### `Exercse 4.1-3`
***
Implement both the brute-force and recursive algorithms for the maximumsubarray
problem on your own computer. What problem size n0 gives the crossover
point at which the recursive algorithm beats the brute-force algorithm? Then,
change the base case of the recursive algorithm to use the brute-force algorithm
whenever the problem size is less than n0. Does that change the crossover point?
### Answer.

    int maximumSubarray(int arr[],int s,int m,int e) {
        int cur = arr[m],mx = arr[m];
        for(int i=m+1;i<=e;i++) {
            cur += arr[i];
            mx = max(mx,cur);
        }
        cur = mx;
        for(int i=m-1;i>=s;i--) {
            cur += arr[i];
            mx = max(mx,cur);
        }
        return mx;
    }
    int maximumSubarrayRecursive(int arr[],int i,int j) {
        if(i > j)
            return 0;
        else if(i == j)
            return arr[i];
        int m = (i+j)/2;
        int left = maximumSubarrayRecursive(arr,i,m);
        int right = maximumSubarrayRecursive(arr,m+1,j);
        int both = maximumSubarray(arr,i,m,j);
        return max(max(left,right),both);
    }
    
### `Exercise 4.1-4`
***
Suppose we change the definition of the maximum-subarray problem to allow the
result to be an empty subarray, where the sum of the values of an empty subarray is 0. How would you change any of the algorithms that do not allow empty subarrays to permit an empty subarray to be the result?
### Answer.
First traverse the array to find if there is any positive element in there. If there is there run the maximum-subarray algorithm otherwise all elements are negative so return the empty set.
### `Exercise 4.1-5`
***
Use the following ideas to develop a nonrecursive, linear-time algorithm for the
maximum-subarray problem. Start at the left end of the array, and progress toward
the right, keeping track of the maximum subarray seen so far. Knowing a maximum
subarray of A[1..j], extend the answer to find a maximum subarray ending at index
j+1 by using the following observation: a maximum subarray of A[1..j+1]
is either a maximum subarray of A[1..j] or a subarray A[1..j+1], for some
1 <= i <= j + 1. Determine a maximum subarray of the form A[i..j+1] in
constant time based on knowing a maximum subarray ending at index j .
### Answer.
The observation is simple at every point while traversing array we have to check whether we can add previous sum to this element or if previous sum is negative then adding to this element will only make it less not more.
    
    int maximumSubarrayLinear(int A[],int n) {
        int maxSum = 0,tempSum = 0;
        for(int i=0;i<n;i++) {
            if(tempSum < 0)
                tempSum = 0;
            tempSum += A[i];
            maxSum = max(maxSum,tempSum);
        }
        return maxSum;
    }




 