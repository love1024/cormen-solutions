### `Exercise 3.1-1`
***
Let f(n) and g(n) be asymptotically nonnegative functions. Using the basic definition
of Θ notation, prove that max(f(n), g(n)) = Θ(f(n) + g(n)).
### Answer.
Let f = max(f(n),g(n)) and n such that f(n) >= 0 & g(n) >= 0    
    
    
    f <= (f(n) + g(n)) , f(n) >= 0 & g(n) >= 0
Also f is max(f(n),g(n) so

    f >= f(n) & f >= g(n)
    2f >= f(n) + g(n)
    f >= (f(n) + g(n))/2
Using both these result

    (f(n) + g(n))/2 <= f <= (f(n) + g(n))
    (f(n) + g(n))/2 <= max(f(n),g(n)) <= (f(n) + g(n))
Here c1 = 1/2 ,c2 = 1, Hence proved that
    
    max(f(n),g(n)) = Θ(f(n) + g(n))