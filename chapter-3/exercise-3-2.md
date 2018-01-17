### `Exercise 3.2-1`
***
Show that if f(n) and g(n) are monotonically increasing functions, then so are
the functions f(n) + g(n) and f(g(n)), and if f(n) and g(n) are in addition
nonnegative, then f(n).g(n) is monotonically increasing.
### Answer.
**f(n)+g(n) is monotonically increasing**  
Given f(n) and g(n) are monotonically increasing so for some n,m if n >= m than f(n) >= f(m) & g(n) >= g(m).

    f(n) >= f(m)
    f(n) + g(n) >= f(m) + g(n) (Adding g(n) both sides)
    f(n) + g(n) >= f(m) + g(m) (As g(m) is less than g(n))
Hence proved.  
**f(g(n)) is monotonically increasing**  
Given f(n) and g(n) are monotonically increasing so for some n,m if n >= m than f(n) >= f(m) & g(n) >= g(m).  

    g(n) >= g(m)
    x >= y (Taking x = g(n) & y = g(m))
    f(x) >= f(y) (As given when x >= y,f(x) >= f(y))
Hence proved.  
**f(n).g(n) is monotonically increasing**  
Given f(n) and g(n) are monotonically increasing so for some n,m if n >= m than f(n) >= f(m) & g(n) >= g(m).  
    
    f(n) >= f(m)
    f(n).g(n) >= f(m).g(n) (As both are non negative)
    f(n).g(n) >= f(m).g(m) (As g(m) is less than g(n)
Hence proved  
### `Exercise 3.2-2`
***
Prove that  
![equation](http://latex.codecogs.com/gif.latex?a%5E%7Blog_bc%7D%20%3D%20c%5E%7Blog_ba%7D)  
### Answer.
Taking left side  
![equation](http://latex.codecogs.com/gif.latex?a%5E%7Blog_bc%7D%20%3D%20a%5E%7B%5Cdfrac%7Blogc%7D%7Blogb%7D%7D%20%3D%20a%5E%7B%5Cdfrac%7Blogc%7D%7Blogb%7D*%5Cdfrac%7Bloga%7D%7Bloga%7D%7D%20%3D%20a%5E%7B%5Cdfrac%7Blogc%7D%7Bloga%7D*%5Cdfrac%7Bloga%7D%7Blogb%7D%7D%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%20a%5E%7Blog_ac*log_ba%7D%20%3D%20%28a%5E%7Blog_ac%7D%29%5E%7Blog_ba%7D%20%3D%20c%5E%7Blog_ba%7D)  
Which is equal to the right hand side. Hence proved  

### `Exercise 3.2-3`
***
Prove equations
### Answer.
**lg(n!) = Θ(nlgn)**  
Taking stirling's approximation equation  
![equation](http://latex.codecogs.com/gif.latex?n%21%20%3D%20%5Csqrt%7B2%5Cpi%20n%7D%7B%5CBig%28%5Cdfrac%7Bn%7D%7Be%7D%5CBig%29%7D%5En%5CBig%281%20&plus;%20%5Ctheta%5CBig%28%5Cdfrac%7B1%7D%7Bn%7D%5CBig%29%5CBig%29)  
Taking f(n) in place of Θ(1/n) assuming f(n) ɛ Θ(1/n)  
![equation](http://latex.codecogs.com/gif.latex?n%21%20%3D%20%5Csqrt%7B2%5Cpi%20n%7D%7B%5CBig%28%5Cdfrac%7Bn%7D%7Be%7D%5CBig%29%7D%5En%5CBig%281%20&plus;%20f%28n%29%5CBig%29)  
Now taking log both sides  
![equation](http://latex.codecogs.com/gif.latex?log%28n%21%29%20%3D%20log%5CBig%28%5Csqrt%7B2%5Cpi%20n%7D%7B%5CBig%28%5Cdfrac%7Bn%7D%7Be%7D%5CBig%29%7D%5En%5CBig%281%20&plus;%20f%28n%29%5CBig%29%5CBig%29)  
Separting equation using log property  
![equation](http://latex.codecogs.com/gif.latex?log%28n%21%29%20%3D%20log%5CBig%28%5Csqrt%7B2%5Cpi%20n%7D%5CBig%29&plus;log%7B%5CBig%28%5Cdfrac%7Bn%7D%7Be%7D%5CBig%29%7D%5En&plus;log%5CBig%281%20&plus;%20f%28n%29%5CBig%29)  
Take power of log to left  
![equation](http://latex.codecogs.com/gif.latex?log%28n%21%29%20%3D%20log%5CBig%28%5Csqrt%7B2%5Cpi%20n%7D%5CBig%29&plus;nlog%7B%5CBig%28%5Cdfrac%7Bn%7D%7Be%7D%5CBig%29%7D&plus;log%5CBig%281%20&plus;%20f%28n%29%5CBig%29)  
Ignoring constants terms  
![equation](http://latex.codecogs.com/gif.latex?log%28n%21%29%20%3D%20log%28n%29&plus;nlog%7B%28n%29%7D&plus;log%28f%28n%29%29)  
We see here the upper or dominate term here is nlogn as other two are lower order terms so  
![equation](http://latex.codecogs.com/gif.latex?log%28n%21%29%20%3D%20%5Ctheta%28nlgn%29)  
Hence proved.  
**n! = ω(2^n)**  
We know that n! = n*(n-1)*(n-2)...2*1  
Also if we replace each term by 2  
n! = 2 * 2 * 2....2 * 2 =   
So it is intuitive that this term will lower bound n! if n>=4 as replacing by lower value possible.  
n! = w(2^n)  
Hence proved.  
**n! = o(n^n)**  
We know that n! = n*(n-1)*(n-2)...2*1  
If we replace each term by n
n! = n * n * n...n * n  
So it is intuitive that this will upper bound n! as replacing by upper value for n>=2  
n! = o(n^n)  
Hence proved.
### `Exercise 3.1-4`
***
Is the function ![equation](http://latex.codecogs.com/gif.latex?%5Clceil%7Blgn%7D%5Crceil%21) polynomially bounded? Is the function [lglgn]! polynomially
bounded?
### Answer.
For a function f(n) to be polynomically bounded than it must satisfy for some c  
    
    f(n) <= cn^k for n >= n'
Taking log on both side  

    lg(f(n)) <= klgn
    lg(f(n)) <= O(lgn)
So It must be upper bounded by lgn  
***
Given ![equation](http://latex.codecogs.com/gif.latex?%5Clceil%7Blgn%7D%5Crceil%21)  
First lets prove that ![equation](http://latex.codecogs.com/gif.latex?%5Clceil%7Blgn%7D%5Crceil%21) = Θ(lgn)  
![equation](http://latex.codecogs.com/gif.latex?%5Clceil%7Blgn%7D%5Crceil%21) >= lgn  
![equation](http://latex.codecogs.com/gif.latex?%5Clceil%7Blgn%7D%5Crceil%21) <= 2lgn 
Hence ![equation](http://latex.codecogs.com/gif.latex?%5Clceil%7Blgn%7D%5Crceil%21) = Θ(lgn) 
From exercise 3.2-3 we know that  
    
    lg(n!) = Θ(nlgn)  
Putting value  ![equation](http://latex.codecogs.com/gif.latex?%5Clceil%7Blgn%7D%5Crceil%21)  
lg(![equation](http://latex.codecogs.com/gif.latex?%5Clceil%7Blgn%7D%5Crceil%21)) = Θ(![equation](http://latex.codecogs.com/gif.latex?%5Clceil%7Blgn%7D%5Crceil%21)lg![equation](http://latex.codecogs.com/gif.latex?%5Clceil%7Blgn%7D%5Crceil%21)) = Θ(lgnlglgn)  
which is greater than **lgn**
So it is not polynomically bounded. 
***
Now given ![equation](http://latex.codecogs.com/gif.latex?%5Clceil%7Blglgn%7D%5Crceil%21)  
putting value ![equation](http://latex.codecogs.com/gif.latex?%5Clceil%7Blglgn%7D%5Crceil%21)  
lg(![equation](http://latex.codecogs.com/gif.latex?%5Clceil%7Blglgn%7D%5Crceil%21)) = Θ(![equation](http://latex.codecogs.com/gif.latex?%5Clceil%7Blglgn%7D%5Crceil%21)lg![equation](http://latex.codecogs.com/gif.latex?%5Clceil%7Blglgn%7D%5Crceil%21)) = Θ(lglgn*lglglgn) = Θ((lglgn)^2) = Θ(lglgn) = Θ(lgn)  
Which is <= O(lgn)  
Hencie it is polynomically bounded.
### `Exercise 3.2-5`
***
Which is asymptotically larger: lg(lg * n) or lg * (lgn)?
### Answer.
Taking lg*n = x, therefor  
lg(lg*n) = lg(x)  
lg*(lgn) = x - 1  as we are applying logarithm inside we are reducing x iteration by 1  
asymptotically x-1 > lg(x), therefore  
lg*(lgn) > lg(lg*n)  
### `Exercise 3.2-6`
***
Show that the golden ratio ɸ and its conjugate ɸ' both satisfy the equation
x^2 = x + 1.
### Answer.
![equation](http://latex.codecogs.com/gif.latex?%5Cphi%20%3D%20%5Cdfrac%7B1%20&plus;%20%5Csqrt5%7D%7B2%7D)  
![equation](http://latex.codecogs.com/gif.latex?%5Cphi%27%20%3D%20%5Cdfrac%7B1%20-%20%5Csqrt5%7D%7B2%7D)  
Putting these value we can see these values satisy equation.  
### `Exercise 3.2-7`
***
Prove by induction that the i th Fibonacci number satisfies the equality  
![equation](http://latex.codecogs.com/gif.latex?F_i%20%3D%20%5Cdfrac%7B%5Cphi%5Ei%20-%20%5Cphi%27%5Ei%7D%7B%5Csqrt5%7D)  
where ɸ is the golden ratio and ɸ' is its conjugate.
### Answer.  
**Base case, suppose its true for i=0 & 1**  
![equation](http://latex.codecogs.com/gif.latex?F_0%20%3D%20%5Cdfrac%7B%5Cphi%5E0%20-%20%5Cphi%27%5E0%7D%7B%5Csqrt5%7D%20%3D%200%5C%5C%20%5Chspace*%7B0.6cm%7DF_1%20%3D%20%5Cdfrac%7B%5Cphi%5E1%20-%20%5Cphi%27%5E1%7D%7B%5Csqrt5%7D%20%3D%20%5Cdfrac%7B%5Cdfrac%7B1&plus;%5Csqrt5%7D%7B2%7D%20-%20%5Cdfrac%7B1-%5Csqrt5%7D%7B2%7D%20%7D%7B%5Csqrt5%7D%20%3D%201)  
Hence it is true for base cases.  
**Now using strong induction suppose its true for Fk, F(k-1),...F0**  
![equation](http://latex.codecogs.com/gif.latex?F_k%20&plus;%20F_%7Bk-1%7D%20%3D%20%5Cdfrac%7B%5Cphi%5Ek%20-%20%5Cphi%27%5Ek%7D%7B%5Csqrt5%7D%20&plus;%20%5Cdfrac%7B%5Cphi%5E%7Bk-1%7D%20-%20%5Cphi%27%5E%7Bk-1%7D%7D%7B%5Csqrt5%7D%20%3D%20%5Cdfrac%7B%5Cphi%5Ek%20-%20%5Cphi%27%5Ek%20&plus;%20%5Cphi%5Ek%5Cphi%5E-1%20-%20%5Cphi%27%5Ek%5Cphi%27%5E-1%7D%7B%5Csqrt5%7D%20%3D%20%5Cdfrac%7B%5Cphi%5Ek%281%20&plus;%20%5Cphi%5E-1%29%20-%20%5Cphi%27%5Ek%281%20&plus;%20%5Cphi%27%5E-1%29%20%7D%7B%5Csqrt5%7D%20%3D%20%5Cdfrac%7B%5Cphi%5Ek%281%20&plus;%20%5Cdfrac%7B2%7D%7B1&plus;%5Csqrt5%7D%29%20-%20%5Cphi%27%5Ek%281%20&plus;%20%5Cdfrac%7B2%7D%7B1-%5Csqrt5%7D%29%20%7D%7B%5Csqrt5%7D%20%3D%20%5Cdfrac%7B%5Cphi%5Ek%28%5Cdfrac%7B3%20&plus;%20%5Csqrt5%7D%7B1&plus;%5Csqrt5%7D%29%20-%20%5Cphi%27%5Ek%28%5Cdfrac%7B3-%5Csqrt5%7D%7B1-%5Csqrt5%7D%29%20%7D%7B%5Csqrt5%7D%20%3D%20%5Cdfrac%7B%5Cphi%5Ek%28%5Cdfrac%7B3%20&plus;%20%5Csqrt5%7D%7B1&plus;%5Csqrt5%7D%29%28%5Cdfrac%7B1%20-%20%5Csqrt5%7D%7B1-%5Csqrt5%7D%29%20-%20%5Cphi%27%5Ek%28%5Cdfrac%7B3-%5Csqrt5%7D%7B1-%5Csqrt5%7D%29%28%5Cdfrac%7B1%20&plus;%20%5Csqrt5%7D%7B1&plus;%5Csqrt5%7D%29%20%7D%7B%5Csqrt5%7D%20%3D%20%5Cdfrac%7B%5Cphi%5Ek%28%5Cdfrac%7B1%20&plus;%20%5Csqrt5%7D%7B2%7D%29%20-%20%5Cphi%27%5Ek%28%5Cdfrac%7B1-%5Csqrt5%7D%7B2%7D%29%20%7D%7B%5Csqrt5%7D%5C%5C%20%3D%20F_%7Bk&plus;1%7D)  
Hence true for k+1  
So by induction this equation is true.
### `Exercise 3.2-8`
***
Show that klnk = Θ(n) implies k = Θ(n/ln n).
### Answer.
Given  
    
    klnk = Θ(n)
    c1n <= klnk <= c2n ..(1)
Taking c1n <= klnk and taking log both sides  

    lgc1 + lgn <= lgk + lglnk
    lgn <= O(lgk)
    lgn <= c3lgk
Now dividing n 
    
    n/lgn >= n/c2lgk
    n/lgn >= k/c2c3 (from equation 1)
    k <= O(n/lgn)  ...(2)
Now taking klnk <= c2n and taking log both sides  as before  
    
    lgn >= Ω(lgk)
    lgn >= c3lgk  
Now dividing n  
    
    n/lgn <= n/c3lgk  
    n/lgn <= k/c2c3 (from equation 1)
    k >= Ω(n/lgn) ...(3)
Using equation 2 & 3  
Hence proved **k = Θ(n/ln n)**.
    
    









