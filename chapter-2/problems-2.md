## Problem 2-1
***

### _Insertion sort on small arrays in merge sort_  
Although merge sort runs in O(nlgn) worst-case time and insertion sort runs in O(n^2) worst-case time, the constant factors in insertion sort can make it faster in practice for small problem sizes on many machines. Thus, it makes sense to coarsen the leaves of the recursion by using insertion sort within merge sort when	subproblems become sufficiently small. Consider a modification to merge sort in which n=k sublists of length k are sorted using insertion sort and then merged using the standard merging mechanism, where k is a value to be determined.

#### `Part a` 
Show that insertion sort can sort the n=k sublists, each of length k, in Θ(nk) worst-case time.  
#### Answer

Sublist each of length k will take in worst case  
&nbsp;&nbsp; ![equation](http://latex.codecogs.com/gif.latex?%5CTheta%28k%5E2%29)   
And there are n/k sublists so time complexity will be  
&nbsp;&nbsp; ![equation](http://latex.codecogs.com/gif.latex?%5CTheta%28n/k%20*%20k%5E2%29%20%3D%20%5Ctheta%28nk%29)
		
#### `Part b`
Show how to merge the sublists in O(nlg(n/k)) worst-case time.  
#### Answer 
We can use the simple merge sort procedure on the coarsed array which will take time as given below.  
If there is no coarsen then the recursion depth will go to full which is to single element so depth will be **lg n**  
But now after coarsen the depth has decreased by **lg k** as k elements are coarsed So now the depth available is  
&nbsp;&nbsp; **lgn - lgk = lg(n/k)** And at each depth the total time will still be O(ck) so the worst-case time complexity in coarsen is **O(nlg(n/k))**

#### `Part c`
Given that the modified algorithm runs in O(nk +  nlg(n/k)) worst-case time, what is the largest value of k  
as a function of n for which the modified algorithm has the same running time as standard merge sort, in terms   
of Θ notation?  
#### Answer 
The modified algorithm should run asymptotically same as orginal when  

    O(nk + nlg(n/k)) = O(nlgn)
This is possible for k = lgn as when we put   

    O(nlgn + nlg(n/lgn))  
    (nlgn + nlgn - nlglgn)  
    O(2nlgn - nlglgn)
which is asymptotically equal to merge sort Value cannot be larget than lgn as if it will then the left hand side  
will become greater than standard merge sort which is not required.

#### `Part d`
How should we choose k in practice?  
#### Answer
In practise K should be large constant smaller than lgn 
on which insertion sort is faster than merge sort. So different values of k 
should be tested.
	
## Problem 2-2
***
### Correctness of Bubblesort
Bubblesort is a popular, but inefficient, sorting algorithm. It works by repeatedly adjacent elements that are out of order.  
 
	Bubblesort(A) {
	 	for(int i=0;i<A.length;i++) {
		 	for(int j=A.length-1;j>i;j--) {
				if(A[j] < A[j-1])
					swap(A[j],A[j-1]);
			}
		}
	}

#### `Part a`
Let A' denote the output of BUBBLESORT(A). To prove that BUBBLESORT is
correct, we need to prove that it terminates and that  
&nbsp;&nbsp; A'[1] <= A'[2] <= .. A'[n] (2.3)  
where n = A.length. In order to show that BUBBLESORT actually sorts, what
else do we need to prove?  
#### Answer
We need to prove that after BUBBLESORT completes the array A' contains the same element as A or A' is permutation of A.  

**The next two parts will prove inequality (2.3)**.  
#### `Part b`
State precisely a loop invariant for the for loop in lines (2-4), and prove that this loop invariant holds. Your proof should use the structure of the loop invariant proof presented in this chapter.  
#### Answer
_Loop Invariant_:  
At the start of each iteration  of loop (2-4) , A[j] is the smallest element in 
array A[j..A.length-1]  
_Initialization_:  
At starting j is at position A.length So A[j] is smallest element as it is only
one.  
_Maintenance_:  
After each iteration j decreases by 1 and before decreasing j line 3 check whether
that the value at current j is less than value j-1 (The one loop is going to), if yes then we swap j with j-1. So j will always be minimum after each iteration as we swap elements to keep minimum value at j.  
_Termination_:  
On termination j will become i and A[i] is smallest element in A[i..n] so invariant holds.  
	
#### `Part c`
Using the termination condition of the loop invariant proved in part (b), state
a loop invariant for the for loop in lines (1-4) that will allow you to prove inequality (2.3). Your proof should use the structure of the loop invariant proof
presented in this chapter.  
#### Answer
_Loop Invariant_:.  
At the start of each iteration of loop (1-4), Array A[1..i-1] contains i-1 smallest elements of array A in sorted order.  
_Initialization_:  
At starting A[1..i-1] will be empty so loop invariant holds true by default.  
_Maintenance_:  
Ater each iteration of outer loop the value at ith position contains smallest element from array A[i..A.length]. Also this was true i-1,i-2..1 so this will be the smallest ith element in the array in sorted order. Hence loop invariant holds after each iteration.  
_Termination_:  
At the end i is equal to A.length and  array A[1..A.lengths] contains A.length smallest element in sorted order or array A[1..A.length] is sorted.   
	
#### `Part d`
What is the worst-case running time of bubblesort? How does it compare to the
running time of insertion sort?  
#### Answer
Both of the outer and inner loop will run A.length times no matter what will be 
the input so worst case time complexity of bubblesort is  
&nbsp;&nbsp; O(n^2)  
In insertion sort find position of element in sorted array so whenever we find 
some element which is not following the If condition we can break out inner loop.
Hence Best case time complexity can be  
&nbsp;&nbsp; O(n)  
But in bubblesort this is not the case as we are finding minimum in unsorted array
so best and worst case both are  
&nbsp;&nbsp; O(n^2)  
		
## Problem 2-3
***
### Correctness of Horner's rule
The following code fragment implements Horner's rule for evaluating a polynomial

![equation](http://latex.codecogs.com/gif.latex?P%28x%29%20%3D%20%5Csum_%7Bk%3D0%7D%5Ena_kx%5Ek%20%5C%5C%20%5Chspace*%7B1.5cm%7D%20%3D%20a_0%20&plus;%20x%28a_1%20&plus;%20x%28a_2%20&plus;%20...%20&plus;%20x%28a_%7Bn-1%7D%20&plus;%20xa_n%29...%29%29)

given the coefficients of a0,a1,...an and a value for x:

    1. y = 0
    2. for i=n downto 0
    3. y = ai + x.y

#### `Part a`
In terms of Θ notation, what is the running time of this code fragment for Horner’s rule?
#### Answer 
As there is only one for loop which is calculating the equation so the running time will be  
&nbsp;&nbsp;Θ(n)

#### `Part b`
Write pseudocode to implement the naive polynomial-evaluation algorithm that computes each term of the polynomial from scratch. What is the running time of this algorithm? How does it compare to Horner’s rule?
#### Answer
    evaluate(a,x) {
        y = 0;
    	for(i=0;i<n;i++) {
    	    t = 1
    	    for(j=0;j<i;j++) {
                t = t*x    
    	    }
    	    y += a[i]*t
    	}
	}
Outer loop will traverse each term and inner loop will find the power of x of that term. So Both loops will time complexity equal to 
    
        O(n^2)
Which is more than Horner's rule.

#### `Part c`
Consider the following loop invariant:
At the start of each iteration of the for loop of lines 2–3,  
![equation](http://latex.codecogs.com/gif.latex?y%20%3D%20%5Csum_%7Bk%3D0%7D%5E%7Bn-%28i&plus;1%29%7Da_%7Bk&plus;i&plus;1%7Dx%5Ek)  
#### Answer
_Initialization_:  
At starting i=n, upper bound will become -1 so for no equation summation will become 0
which is true as y=0 before first iteration.  
_Maintenance_:  
At the end of some ith loop ai will be added  
![equation](http://latex.codecogs.com/gif.latex?a_i%20&plus;%20%5Csum_%7Bk%3D0%7D%5E%7Bn-%28i&plus;1%29%7Da_%7Bk&plus;i&plus;1%7Dx%5Ek%3Da_i%20&plus;%20x%5Csum_%7Bk%3D1%7D%5E%7Bn-%28i&plus;1%29%7Da_%7Bk&plus;i&plus;1%7Dx%5E%7Bk-1%7D%20%3D%20%5Csum_%7Bk%3D0%7D%5E%7Bn-i%7Da_%7Bk&plus;i%7Dx%5Ek)  
So loop invariant holds true.  
_Termination_:  
At end i = -1 so  
![equation](http://latex.codecogs.com/gif.latex?%5Csum_%7Bk%3D0%7D%5E%7Bn%7Da_%7Bk%7Dx%5Ek)  
Which is the required Horner rule.
#### `Pard d`
Conclude by arguing that the given code fragment correctly evaluates a polynomial
characterized by the coefficients a0,a1,...an.
#### Answer
We just proved that the termination of algorithm will generate Horner rule which is the required result.

## Problem 2-4
***
### Inversion
Let A[1..n] be an array of n distinct numbers. If i < j and A[i] > A[j], then the
pair (i,j) is called an inversion of A.
#### `Part a`
List the five inversions of the array {2, 3, 8, 6, 1}.
#### Answer
(2,1), (3,1), (8,6), (6,1) & (8,1)
#### `Part b`
What array with elements from the set {1,2,...n} has the most inversions?
How many does it have?
#### Answer
The array A[n,n-1...1] has most inversion and these are 

    n(n-1)/2
#### `Part c`
What is the relationship between the running time of insertion sort and the
number of inversions in the input array? Justify your answer.
#### Answer
The number of inversion are proportional to the inner while loop of insertion sort.Inner while loop only run whenever there is j < i such that A[j] > A[i] and it forms a inversion also. So running time of insertion sort is proportional to the inversions of the array. More the inversions more will be the running time.
#### `Part d`
Give an algorithm that determines the number of inversions in any permutation
on n elements in Θ(nlgn) worst-case time. (Hint: Modify merge sort.)
#### Answer
    inv = 0;
    merge(A,s,m,e) {
        i=s,j=m+1,k=0;
        B[e-s+1];
        while(i <= m && j<= e) {
            if(A[i] <= A[j]) {
                B[k] = A[i];
                i++;
            } else {
                B[k] = A[j];
                j++;
                inv += (m-s+1); //Here inversion count
            }
            k++;
        }
        while( i<= m) {
            B[k] = A[i];
            i++,k++;
        }
        while( j<= e) {
            B[k] = A[j];
            j++,k++;
        }
        for(int i=0;i<=e-s;i++) {
            A[i+s] = B[i]; 
        }
    }
    
