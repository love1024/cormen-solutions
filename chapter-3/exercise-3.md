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
We have to find value of c1 & c2 to prove the result. Bascially there are two cases  
**when a > 0**  
Let a be equal to n such that  
![equation](http://latex.codecogs.com/gif.latex?%28n&plus;a%29%5Eb%20%3D%20%28n%20&plus;%20n%29%5Eb%20%3D%202%5Ebn%5Eb)  
**when a < 0**  
Let a be equal to n/2 such that  
![equation](http://latex.codecogs.com/gif.latex?%28n&plus;a%29%5Eb%20%3D%20%28n%20-%20n/2%29%5Eb%20%3D%202%5E%7B-b%7Dn%5Eb)  
So given equation is bounded above and below by these results  
![equation](http://latex.codecogs.com/gif.latex?2%5E%7B-b%7Dn%5Eb%20%3C%3D%20%28n&plus;a%29%5Eb%20%3C%3D%202%5Ebn%5Eb%5C%5C%20%5Chspace*%7B0.6cm%7Dc1%20%3D%202%5E%7B-b%7D%20%2C%20c2%20%3D%202%5Eb)  
Hence it is proved that  
![equation](http://latex.codecogs.com/gif.latex?%28n&plus;a%29%5Eb%20%3D%20%5Ctheta%28n%5Eb%29).

