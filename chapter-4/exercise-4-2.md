 ### `Exercise 4.2-1`
***
Use Strassen’s algorithm to compute the matrix product  
![equation](http://latex.codecogs.com/gif.latex?%5Cbegin%7Bpmatrix%7D%201%20%26%203%5C%5C%207%20%26%205%20%5Cend%7Bpmatrix%7D%20%5Cbegin%7Bpmatrix%7D%206%20%26%208%5C%5C%204%20%26%202%20%5Cend%7Bpmatrix%7D)  
Show your work.  
### Answer.
First find sum terms  
S1 = 8-2 = 6  
S2 = 1+3 = 4  
S3 = 7+5 = 12  
S4 = 4-6 = -2  
S5 = 1+5 = 6  
S6 = 6+2 = 8  
S7 = 3-5 = -2  
S8 = 4+2 = 6  
S9 = 1-7 =-6  
S10 = 6+8 = 14  
Now find product terms  
P1 = 1.6 = 6  
P2 = 4.2 = 8  
P3 = 12.6 = 72  
P4 = -2.5 = -10  
P5 = 6.8 = 48  
P6 = -2.6 = -12  
P7 = -6.14 = -84  
Now find the terms of matrix  
C11 = 48 - 10 - 8 -12 = 18  
C12 = 14  
C21 = 62  
C22 = 48 + 6 - 72 + 84 = 66  
Se result matrix is  
![equation](http://latex.codecogs.com/gif.latex?%5Cbegin%7Bpmatrix%7D%2018%20%26%2014%5C%5C%2062%20%26%2066%20%5Cend%7Bpmatrix%7D)  
### `Exercise 4.2-2`
***
Write pseudocode for Strassen’s algorithm.  
### Answer.

    StrassenMatrixMultiplication(A,B) {
        n = A.rows;
        C = [n][n];
        if(n == 1)
            c11 = a11.b11;
        else Partition A,B and C as in equation 4.9 in next chapter
        S1=S2=S3=S4=S5=S6=S7=S8=S9=S10 = [n/2][n/2];
        P1=P2=P3=P4=P5=P6=P7 = [n/2][n/2];
        
        //Calculate sum terms
        S1  = B12 - B22;
        S2  = A11 + A12;
        S3  = A21 + A22;
        S4  = B21 - B11;
        S5  = A11 + A22;
        S6  = B11 + B22;
        S7  = A12 - A22;
        S8  = B21 + B22;
        S9  = A11 - A21;
        S10 = B11 + B12;
        
        //Calculate product terms
        P1  = StrassenMatrixMultiplication(A11, S1);
        P2  = StrassenMatrixMultiplication(S2, B22);
        P3  = StrassenMatrixMultiplication(S3, B11);
        P4  = StrassenMatrixMultiplication(A22, S4);
        P5  = StrassenMatrixMultiplication(S5, S6);
        P6  = StrassenMatrixMultiplication(S7, S8);
        P7  = StrassenMatrixMultiplication(S9, S10);
        
        //Calcuate the result matrix terms
        C11 = P4 + P5 + P6 - P2;
        C12 = P1 + P2;
        C21 = P3 + P4;
        C22 = P1 + P5 - P3 - P7;
        return C;
    }
### `Exercise 4.2-3`
***
How would you modify Strassen’s algorithm to multiply n	n matrices in which n
is not an exact power of 2? Show that the resulting algorithm runs in time n^lg7?
### Answer.
Just pad the matrix with zeroes to make it power of 2. The number of terms in matrix can increase by 2 times but still the run time complexity will be same.  

    (2n)^lg7 = 7.n^lg7 = Θ(n^lg7)
So it will only increase by a constant factor.
### `Exercise 4.2-4`
***
What is the largest k such that if you can multiply 3 	 3 matrices using k multiplications
(not assuming commutativity of multiplication), then you can multiply
nXn matrices in time o(nlg7)? What would the running time of this algorithm be?
### Answer.
If only k multiplications steps are required for problem of size n/3 then recursive running time is given by
    
    T(n) = k*T(n/3) + O(n^2)
Using master method the running time can be given by lg_3k so we should choose k such that  
    
    lg_3k < lg7
so k shoudl be equal to 21.  
### `Exercise 4.2-5`
***
V. Pan has discovered a way of multiplying 68X68 matrices using 132,464 multiplications,
a way of multiplying 70X70 matrices using 143,640 multiplications,
and a way of multiplying 72X72 matrices using 155,424 multiplications. Which
method yields the best asymptotic running time when used in a divide-and-conquer
matrix-multiplication algorithm? How does it compare to Strassen’s algorithm?
### Answer.
Here we are diving the problem into size of 68,70 and 72 with each have its own multiplication number. using recursive running time we can get  
    
    132464*T(n/68) + O(n^2) = lg_68(132464) = 2.795128  
    143640*T(n/70) + O(n^2) = lg_70(143640) = 2.795122
    155424*T(n/72) + O(n^2) = lg_72(155424) = 2.795147
We see that second method yied best asymptotic running time and it is less than the strassen's algoritm running time as

    lg7 > 2.8 > 2.795122
### `Exercise 4.2-6`
***
How quickly can you multiply a knXn matrix by an nXkn matrix, using Strassen’s
algorithm as a subroutine? Answer the same question with the order of the input
matrices reversed.
### Answer.
If we will multiply knXn matrix with nXkn matrix we will get kn X Kn matrix in which there will k^2 nXn matrices. nXn matrices can be solved using strassen algorithm with O(n^lg7) compelxity so overall compelxity will be
    
    O(k^2 * n^lg7)
If we will reverse the order such as multiply nXkn matrix with KnXn matrix we will get nXn matrix which we can solve using straseen algorithm. But to find each term of nXn matrix we still have to do K times work. SO overall complexity will be.  
    
    O(k * n^lg7)
### `Exercise 4.2-7`
***
Show how to multiply the complex numbers a + bi and c + di using only three
multiplications of real numbers. The algorithm should take a, b, c, and d as input
and produce the real component ac - bd and the imaginary component ad + bc
separately.
### Answer.
We can use the following equation  
    
    (a+b)(c+d) = ac + ad + bc + bd
               = ac + bd + ad + bc
    (a+b)(c+d) - ac - bd = ad + bc  ...(1)
    let S1 = a+b
        S2 = c+d
        P1 = S1 * S2
        P2 = ac
        P3 = bd
So we will only need to find these three products P1,P2 and P3 and real and imaginary component can be given by  
    
    (P2 - P3) + i(P1 - P2 - P3)
    (ac - bd) + i(ad + bc) (from equation 1)

