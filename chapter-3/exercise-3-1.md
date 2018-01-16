### `Exercise 3.1-1`
***
Let f(n) and g(n) be asymptotically nonnegative functions. Using the basic definition
of Θ notation, prove that max(f(n), g(n)) = Θ(f(n) + g(n)).
### Answer.
Let f = max(f(n),g(n)) and n such that f(n) >= 0 & g(n) >= 0    
    
    
    f <= (f(n) + g(n)) , f(n) >= 0 & g(n) >= 0
Also f is max(f(n),g(n)) so

    f >= f(n) || f >= g(n)
    2f >= f(n) + g(n)
    f >= (f(n) + g(n))/2
Using both these result

    (f(n) + g(n))/2 <= f <= (f(n) + g(n))
    (f(n) + g(n))/2 <= max(f(n),g(n)) <= (f(n) + g(n))
Here c1 = 1/2 ,c2 = 1, Hence proved that
    
    max(f(n),g(n)) = Θ(f(n) + g(n))
    
### `Exercise 3.1-2`
***
Show that for any real constants a and b, where b > 0,  
![equation](http://latex.codecogs.com/gif.latex?%28n&plus;a%29%5Eb%20%3D%20%5Ctheta%28n%5Eb%29).
### Answer.
We have to find value of c1 , c2 & n to prove the result. Bascially there are two cases  
**when a > 0**  
Let a be equal to n such that  
![equation](http://latex.codecogs.com/gif.latex?%28n&plus;a%29%5Eb%20%3D%20%28n%20&plus;%20n%29%5Eb%20%3D%202%5Ebn%5Eb)  
**when a < 0**  
Let a be equal to n/2 such that  
![equation](http://latex.codecogs.com/gif.latex?%28n&plus;a%29%5Eb%20%3D%20%28n%20-%20n/2%29%5Eb%20%3D%202%5E%7B-b%7Dn%5Eb)  
So given equation is bounded above and below by these results if we take n >= 2a  
![equation](http://latex.codecogs.com/gif.latex?2%5E%7B-b%7Dn%5Eb%20%3C%3D%20%28n&plus;a%29%5Eb%20%3C%3D%202%5Ebn%5Eb%5C%5C%20%5Chspace*%7B0.6cm%7Dc1%20%3D%202%5E%7B-b%7D%20%2C%20c2%20%3D%202%5Eb)  
Hence it is proved that  
![equation](http://latex.codecogs.com/gif.latex?%28n&plus;a%29%5Eb%20%3D%20%5Ctheta%28n%5Eb%29).

### `Exercise 3.1-3`
***
Explain why the statement, “The running time of algorithm A is at least O(n^2)" is
meaningless.
### Answer
O(n) is used to describe the upper bound on the running time of algorithm that means there exist some value c such that running time T is upper bounded by  

    T <= cO(n)  
    
The least value of T can be O(1) but T != O(1) as O(n) describe the upper bound not the least value so statement is meaningless.  

### `Exercise 3.1-4`
***
![equation](http://latex.codecogs.com/gif.latex?%5Ctext%7BIs%20%7D%202%5E%7Bn&plus;1%7D%20%3D%20O%282%5En%29%20%3F%20%5Ctext%7B%20Is%20%7D%202%5E%7B2n%7D%20%3D%20O%282%5En%29%3F) 
### Answer,
Rewriting the equation as  
![equation](http://latex.codecogs.com/gif.latex?2.2%5En%20%3C%3D%20c.O%282%5En%29)  
Taking c as at least 2 we can see this is a valid equation.   
Also rewriting the second equation  
![equation](http://latex.codecogs.com/gif.latex?2%5E%7B2n%7D%20%3D%202%5En.2%5En%20%3C%3D%20c.O%282%5En%29)  
Which is not possible as c cannot be greater than 2^n as c is constant hence this equation is not valid.

### `Exercise 3.1-5`
***
Prove Theorm 3.1
### Answer  
**Theorm states that**:  
For any two functions f(n) and g(n), we have f(n) = Θ(g(n)) if and only if  
![equation](http://latex.codecogs.com/gif.latex?f%28n%29%20%3D%20O%28g%28n%29%29%20%5Ctext%7B%20and%20%7D%20f%28n%29%20%3D%20%5COmega%20g%28n%29)  
We have to prove it both ways to prove this  
**Assuming**  
![equation](http://latex.codecogs.com/gif.latex?f%28n%29%20%3D%20%5Ctheta%20g%28n%29)  
So there exist some c1,c2 and n' such that  

    0 <= c1.g(n) <= f(n) <= c2.g(n) , n > n'
As c1.g(n) <= f(n) & f(n) <= c2.g(n) for some c1,c2 and n'  
![equation](http://latex.codecogs.com/gif.latex?f%28n%29%20%3D%20O%28g%28n%29%29%20%5Ctext%7B%20and%20%7D%20f%28n%29%20%3D%20%5COmega%20g%28n%29)  
**Now  Assuming**  

![equation](http://latex.codecogs.com/gif.latex?f%28n%29%20%3D%20O%28g%28n%29%29%20%5Ctext%7B%20and%20%7D%20f%28n%29%20%3D%20%5COmega%20g%28n%29)  

So using these  

    f(n) <= c2.g(n) for some n>n1
    f(n) >= c1.g(n) for some n>n2
    0 <= c1.g(n) <= f(n) <= c2.g(n) for n > max(n1,n2)
Hence proved.

### `Exercise 3.1-6`
***
Prove that the running time of an algorithm is Θg(n) if and only if its worst-case
running time is O(g(n)) and its best-case running time is Omega(g(n)).
### Answer.
Same as exercise 3.1-5.

### `Exercise 3.1-7`
***
![equation](http://latex.codecogs.com/gif.latex?%5Ctext%7Bprove%20that%20%7D%20o%28g%28n%29%29%5Ccap%5Comega%20%28g%28n%29%29%20%5Ctext%7B%20is%20the%20empty%20set%7D)  
### Answer.
Let f(n) be the function upper and lower bound by given functions  

    f(n) < o(g(n)) & f(n) > w(g(n))
As f(n) cannot be equal to these functions so disjunction of these function is empty set.

### `Exercise 3.1-8`
***
We can extend our notation to the case of two parameters n and m that can go to
infinity independently at different rates. For a given function g(n,m) we denote
by O(g(n,m)) the set of functions  

    O(g(n,m)) = {f(n,m): there exist positive constants c,n',m' 
                 such that  0<= f(n,m) <= cg(n,m)
                 for all n>n' or m>=m'}
Give corresponding definitions for Ω(g(n,m)) and Θ(g(n,m)).
### Answer.
    
    Ω(g(n,m)) = {f(n,m): there exist positive constants c,n',m'
                 such that 0 <= cg(n,m) <= f(n,m)
                 for all n>= n' and m>= m'}
    
    Θ(g(n,m)) = {f(n,m): there exist positive constants c1,c2,n',m'
                 such that 0 <= c1g(n,m) <= f(n,m) <= c2g(n,m)
                 for all n>= n' and m>= m'}





