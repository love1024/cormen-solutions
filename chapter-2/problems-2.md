Q 2-1
	Insertion sort on small arrays in merge sort
	Although merge sort runs in O(nlgn) worst-case time and insertion sort runs
	in O(n^2) worst-case time, the constant factors in insertion sort can make it faster
	in practice for small problem sizes on many machines. Thus, it makes sense to
	coarsen the leaves of the recursion by using insertion sort within merge sort when
	subproblems become sufficiently small. Consider a modification to merge sort in
	which n=k sublists of length k are sorted using insertion sort and then merged
	using the standard merging mechanism, where k is a value to be determined.

	a.	
		Show that insertion sort can sort the n=k sublists, each of length k, in Θ(nk)
		worst-case time.
	A	
		Sublist each of length k will take in worst case
			O(k^2) 
		And there are n/k sublists so time complexity will be 
			O(n/k * k^2) = O(nk). 
			
	b.	
		Show how to merge the sublists in O(nlg(n/k)) worst-case time.
	A	
		We can use the simple merge sort procedure on the coarsed array 
		which will take time as given below:
		If there is no coarsen then the recursion depth will go to full 
		which is to single element so depth will be
			lgn
		But now after coarsen the depth has decreased by 
			lgk
		as k elements are coarsed So now the depth available is 
			lgn - lgk = lg(n/k)
		And at each depth the total time will still be O(ck) so the worst-case
		time complexity in coarsen is 
			O(nlg(n/k))
	
	c.
		Given that the modified algorithm runs in O(nk +  nlg(n/k)) worst-case time,
		what is the largest value of k as a function of n for which the modified algorithm
		has the same running time as standard merge sort, in terms of Theta notation?
	A 	
		The modified algorithm should run asymptotically same as orginal when 
			O(nk + nlg(n/k)) = O(nlgn)
		This is possible for k = lgn as when we put 
			O(nlgn + nlg(n/lgn)) 
			O(nlgn + nlgn - nlglgn)
			O(2nlgn - nlglgn) 
		which is asymptotically equal to merge sort 
		Value cannot be larget than lgn as if it will then the left hand side 
		will become greater than standard merge sort which is not required.
	
	d. 
		How should we choose k in practice?
	A 
		In practise K should be large constant smaller than lgn 
		on which insertion sort is faster than merge sort. So different values of k 
		should be tested.
		
Q 2-2 
	Bubblesort is a popular, but inefficient, sorting algorithm. It works by repeatedly
	adjacent elements that are out of order.
	Bubblesort(A) {
	1	for(int i=0;i<A.length;i++) {
	2		for(int j=A.length-1;j>i;j--) {
	3			if(A[j] < A[j-1])
	4				swap(A[j],A[j-1]);
			}
		}
	}
	
	a.
		Let A' denote the output of BUBBLESORT(A). To prove that BUBBLESORT is
		correct, we need to prove that it terminates and that
		A'[1] <= A'[2] <= .. A'[n] (2.3)
		where n = A.length. In order to show that BUBBLESORT actually sorts, what
		else do we need to prove?
	A
		We need to prove that after BUBBLESORT completes the array A' contains the 
		same element as A or A' is permutation of A.
	
	The next two parts will prove inequality(2.3).
	b.
		State precisely a loop invariant for the for loop in lines (2-4), and prove that this
		loop invariant holds. Your proof should use the structure of the loop invariant
		proof presented in this chapter.
	A 
		Loop Invariant:
		At the start of each iteration  of loop (2-4) , A[j] is the smallest element in 
		array A[j..A.length-1]
		
		Initialization:
		At starting j is at position A.length So A[j] is smallest element as it is only
		one.
		
		Maintenance:
		After each iteration j decreases by 1 and before decreasing j line 3 check whether
		that the value at current j is less than value j-1 (The one loop is going to), if yes
		then we swap j with j-1. So j will always be minimum after each iteration as we swap 
		elements to keep minimum value at j.
		
		Termination:
		On termination j will become i and A[i] is smallest element in A[i..n] so invariant holds.
		
	c.
		Using the termination condition of the loop invariant proved in part (b), state
		a loop invariant for the for loop in lines (1-4) that will allow you to prove inequality
		(2.3). Your proof should use the structure of the loop invariant proof
		presented in this chapter.
	A
		Loop Invariant:
		At the start of each iteration of loop (1-4), Array A[1..i-1] contains i-1 smallest 
		elements of array A in sorted order.
		
		Initialization:
		At starting A[1..i-1] will be empty so loop invariant holds true by default.
		
		Maintenance:
		Ater each iteration of outer loop the value at ith position contains smallest element 
		from array A[i..A.length]. Also this was true i-1,i-2..1 so this will be the smallest
		ith element in the array in sorted order. Hence loop invariant holds after each iteration.
		
		Termination:
		At the end i is equal to A.length and  array A[1..A.lengths] contains A.length smallest 
		element in sorted order or array A[1..A.length] is sorted.
		
	d. 
		What is the worst-case running time of bubblesort? How does it compare to the
		running time of insertion sort?
	A 
		Both of the outer and inner loop will run A.length times no matter what will be 
		the input so worst case time complexity of bubblesort is 
			O(n^2)
		In insertion sort find position of element in sorted array so whenever we find 
		some element which is not following the If condition we can break out inner loop.
		Hence Best case time complexity can be 
			O(n) 
		But in bubblesort this is not the case as we are finding minimum in unsorted array
		so best and worst case both are 
			O(n^2)
			
Q.2-3 
	Correctness of Horner's rule
	The following code fragment implements Horner's rule for evaluating a polynomial
	
![equation](http://latex.codecogs.com/gif.latex?%5Csum_%7Bk%3D0%7D%5E%7Bn-%28i&plus;1%29%7Da_%7Bk&plus;i&plus;1%7Dx%5Ek)
	
		