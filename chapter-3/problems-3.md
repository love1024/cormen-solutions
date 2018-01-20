### `Problme 3-1`
***
Let  
![equation](http://latex.codecogs.com/gif.latex?p%28n%29%20%3D%20%5Csum_%7Bi%3D0%7D%5Eda_in%5Ei)  
where ad > 0, be a degree-d polynomial in n, and let k be a constant. Use the
definitions of the asymptotic notations to prove the following properties.
### Answer.
**A. if k>=d ,then p(n) = O(n^k)**  
Let there are c1,n' such that
    
    p(n) <= c1 * n^k, for n >= n'
Expanding p(n)  
![equation](http://latex.codecogs.com/gif.latex?a_0%20&plus;%20a_1n%5E1%20&plus;%20a_2n%5E2%20&plus;%20...%20a_nn%5En%20%3C%3D%20c_1n%5Ek)  
Dividing both sides by n^k  
![equation](http://latex.codecogs.com/gif.latex?%5Cdfrac%7Ba_0%7D%7Bn%5Ek%7D%20&plus;%20%5Cdfrac%7Ba_1n%5E1%7D%7Bn%5Ek%7D%20&plus;%20%5Cdfrac%7Ba_2n%5E2%7D%7Bn%5Ek%7D%20&plus;%20...%20%5Cdfrac%7Ba_nn%5En%7D%7Bn%5Ek%7D%20%3C%3D%20c_1)  
Now as k >= d so all n^i terms must be <= 1 , therefor  
![equation](http://latex.codecogs.com/gif.latex?a_0%20&plus;%20a_1%20&plus;%20a_2%20...%20a_n%3C%3D%20c_1)  
We have c1 and n' >= 1,  Hence proved  
p(n) = O(n^k)  
**B. if k<=d ,then p(n) = Ω(n^k)**  
Let there are c1,n' such that  

    p(n) >= c1 * n^k , for n>= n'
Expanding p(n) 
![equation](http://latex.codecogs.com/gif.latex?a_0%20&plus;%20a_1n%5E1%20&plus;%20a_2n%5E2%20&plus;%20a_3n%5E3%20&plus;%20...%20&plus;%20a_nn%5En%20%3E%3D%20c_1n%5Ek)  
Now dividing both sides by n^k  
![equation](http://latex.codecogs.com/gif.latex?%5Cdfrac%7Ba_0%7D%7Bn%5Ek%7D%20&plus;%20%5Cdfrac%7Ba_1n%5E1%7D%7Bn%5Ek%7D%20&plus;%20%5Cdfrac%7Ba_2n%5E2%7D%7Bn%5Ek%7D%20&plus;%20...%20&plus;%20%5Cdfrac%7Ba_nn%5En%7D%7Bn%5Ek%7D%20%3E%3D%20c_1)  
Now all the terms of i<= k will become <= 1  so choosing c1 = ak will always keep it lower than other terms.  
![equation](http://latex.codecogs.com/gif.latex?c_1%20%3D%20a%5Ek)  
Hence proved  for c1 = a^k ^ n' = 1
p(n) = Ω(n^k)  
**C. if k = d , then p(n) = Θ(n^k)**  
Using points a & b we can conclude that  

    p(n) = Θ(n^k)
**D. if k > d, then p(n) = o(n^k)**  
We can prove it using limit notation  
![equation](http://latex.codecogs.com/gif.latex?%5Clim_%7Bn%20-%3E%20%5Cinfty%7D%20%5Cdfrac%7Bp%28n%29%7D%7Bn%5Ek%7D%20%3D%20%5Clim_%7Bn%20-%3E%20%5Cinfty%7D%20%5Cdfrac%7B%5Csum_%7Bi%3D0%7D%5Eda_in%5Ei%7D%7Bn%5Ek%7D%20%3D%20%5Clim_%7Bn%20-%3E%20%5Cinfty%7D%20%5Cdfrac%7Ba_dn%5Ed%7D%7Bn%5Ek%7D%20%3D%200)  
Last term is equal to zero as k > d. Hence proved  
p(n) = o(n^k)  
**E. if k > d, then p(n) = ω(n^k)**  
We can prove it using limit notation  
![equation](http://latex.codecogs.com/gif.latex?%5Clim_%7Bn%20-%3E%20%5Cinfty%7D%20%5Cdfrac%7Bp%28n%29%7D%7Bn%5Ek%7D%20%3D%20%5Clim_%7Bn%20-%3E%20%5Cinfty%7D%20%5Cdfrac%7B%5Csum_%7Bi%3D0%7D%5Eda_in%5Ei%7D%7Bn%5Ek%7D%20%3D%20%5Clim_%7Bn%20-%3E%20%5Cinfty%7D%20%5Cdfrac%7Ba_dn%5Ed%7D%7Bn%5Ek%7D%20%3D%20%5Cinfty)  
As d > k therefor numerator is greater tha denominator. Hence proved.  
### `Problem 3-2`
***
Indicate, for each pair of expressions (A,B) in the table below, whether A is O, o,
Ω, w  or Θ‚ of B. Assume that k >=1, e > 0, and c > 1 are constants. Your answer
should be in the form of the table with “yes” or “no” written in each box.
### Answer.

        A       B       O       o       Ω       w       Θ
        lg^kn  n^e     yes     yes     no      no      no
        n^k    c^n     yes     yes     no      no      no
       sqrt(n) n^sinn  no      no      no      no      no
       2^n     2^n/2   no      no      yes     yes     no
       n^lgc   c^lgn   yes     no      yes     no      yes
       lg(n!)  lg(n^n) yes     no      yes     no      yes
### `Problem 3-3`
***
Rank the following functions by order of growth; that is, find an arrangement
g1, g2,...g30 of the functions satisfying g1 = Ω(g2), g2 = Ω(g3), ...,
g29 = Ω(g30) Partition your list into equivalence classes such that functions
f(n) and g(n) are in the same class if and only if f(n)  = Θ(g(n)).
### Answer.
![equation](http://latex.codecogs.com/gif.latex?%5Chspace*%7B-0.65cm%7D2%5E%7B2%5E%7Bn%20&plus;%201%7D%7D%5C%5C%202%5E%7B2%5En%7D%5C%5C%20%28n%20&plus;%201%29%21%5C%5C%20n%21%5C%5C%20e%5En%5C%5C%20n.2%5En%5C%5C%202%5En%5C%5C%20%5Cleft%28%5Cfrac%203%202%5Cright%29%5En%5C%5C%20n%5E%7B%5Clg%20%5Clg%20n%7D%20%3D%20%28%5Clg%20n%29%5E%7B%5Clg%20n%7D%5C%5C%20%28%5Clg%20n%29%21%5C%5C%20n%5E3%5C%5C%20n%5E2%20%3D%204%5E%7B%5Clg%20n%7D%5C%5C%20lg%28n%21%29%20%3D%20n%20%5Clg%20n%5C%5C%202%5E%7B%5Clg%20n%7D%20%3D%20n%5C%5C%20%5Cleft%28%5Csqrt%202%5Cright%29%5E%7B%5Clg%20n%7D%5C%5C%202%5E%7B%5Csqrt%20%7B2%20%5Clg%20n%7D%7D%5C%5C%20%5Clg%5E2%20n%5C%5C%20%5Cln%20n%5C%5C%20%5Csqrt%20%7B%5Clg%20n%7D%5C%5C%20%5Cln%20%5Cln%20n%5C%5C%202%5E%7B%5Clg%5E*%20n%7D%5C%5C%20%5Clg%5E*%20n%20%3D%20lg%5E*%28%5Clg%20n%29%5C%5C%20%5Clg%28%5Clg%5E*%20n%29%29%5C%5C%201%20%3D%20n%5E%7B1/%5Clg%20n%7D%5C%5C)  
**b.Give an example of a single nonnegative function f(n) such that for all functions
g(n) in part (a), f(n) is neither O(n) nor g(n).**  
### `Exercise 3-3`
***
Let f(n) and g(n) be asymptotically positive functions. Prove or disprove each of
the following conjectures.  
**a. _f(n) = O(g(n)) implies g(n) = O(f(n))_**  
False.  
Disproving by counter example. Take value of f(n) = n & g(n) = n^2, we can see that f(n) = O(g(n)) but opposite is not true.  
**b. _f(n)+g(n) = Θ(min(f(n),g(n)))._**  
False. 
Disproving by counter example. Take value of f(n) = n & g(n) = n^2, we can see that _f(n)+g(n) = Ω(min(f(n),g(n))) = Ω(f(n))_ but  _f(n)+g(n) != O(min(f(n),g(n))) != O(f(n))_.  
**c._f(n) = O(g(n))_ implies _lg(f(n)) = O(lg(g(n)))_, where lg(g(n)) > 1 and
f(n) >= 1 for all sufficiently large n.**  
True.  
Given _f(n) = O(g(n))_ so that _f(n) <= c1g(n)_ for some constant c1 and n >= n'  
Taking lg both sides  
_lg(f(n)) <= lg(c1) + lg(g(n))_  
_lg(f(n)) <= c2lg(g(n))_ for some constant c2  
_lg(f(n)) = O(lg(g(n)))_  
**d._f(n) = O(g(n))_ implies _2^f(n) = O(2^g(n))_**  
False.  
Diproving by counter example. Taking _f(n) = 2n & g(n) = n_ as _f(n) = O(g(n))_  
_2n <= c1n_  
_2^2n <= 2^c1n_ taking power of 2 both sides  
_4^n <= 2^c1n_  
4^f(n) != O(2^g(n))  
**e._f(n) = O((f(n))^2)_**  
False.  
Disproving by counter example. Taking _f(n) = 1/n_  
_1/n !<= O(1/n^2)_  
_f(n) !<= O((f(n))^2)_  
**f._f(n) = O(g(n))_ implies _g(n) = Ω(f(n))_**  
True.  
_f(n) <= c1g(n)_  for some constant c1  
_g(n) >= 1/c1 * f(n)_  
_g(n) >= c2 * f(n)_ for some constant c2  
_g(n) = Ω(f(n))_  
**g._f(n) = Θ(f(n/2))_**  
False.  
Diproving by counter example.Taking f(n) = 2^2n so that f(n/2) = 2^n.Now if  
_f(n) = O(f(n/2))_  
_2^2n <= 2^n_  
_4^n <= 2^n_  
which is not true.  
**f._f(n) + o(f(n)) = Θ(f(n))_**  
True.  
Let _g(n) = o(f(n))_  
As _g(n) > 0 && f(n) > 0_  for some n>n'  
_f(n) + g(n) >= f(n)_
_f(n) + g(n) = Ω(f(n))_  
Also _g(n) <= f(n)_  
_f(n) + g(n) <= 2f(n)_  
_f(n) + g(n) = O(f(n))_  
Hence _f(n) + g(n)  = Θ(f(n))_  








    




