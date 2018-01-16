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

