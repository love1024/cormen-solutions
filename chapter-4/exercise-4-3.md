### `Exercise 4.3-1`
***
Show that the solution of T(n) = T(n-1) + n is O(n^2).
### Answer.
Lets assume that T(n) <= cn^2  
    
    T(n) <= c(n-1)^2 + n
    T(n) <= c(n^2 + 1 -2n) + n
    T(n) <= cn^2 + c - 2nc + n
    T(n) <= cn^2 - n(2c - 1) + c
    T(n) <= n^2 - n + 1  ( assume c = 1)
    T(n) <= n^2
which is true for n>=1
### `Exercise 4.3-2`
***
Show that the solution of ![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3D%20T%28%5Clceil%20n/2%20%5Crceil%29%20&plus;%201%20%5Ctext%7B%20is%20%7D%20O%28lgn%29)  
### Answer.
First lets assume that T(n) <= clgn  
![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3C%3D%20clg%28%5Clceil%20n/2%20%5Crceil%29%20&plus;%201%20%3C%3D%20clg%28n/2%20&plus;%201%29%20&plus;%201%20%3D%20clg%28n&plus;2%29%20-%20clg2%20&plus;%201)  
which is inconsistent with induction proof so lets assume T(n) <= clg(n - 2)  
![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3C%3D%20clg%28%5Clceil%20n/2%20%5Crceil%20-%202%29%20&plus;%201%20%3C%3D%20clg%28n/2%20-%201%29%20&plus;%201%20%3D%20clg%28n-2%29%20-%20clg2%20&plus;%201%20%3C%3D%20clg%28n-2%29)  
for c >= 1
### `Exercise 4.3-3`
***
We saw that the solution of ![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3D%202T%28%5Clfloor%20n/2%20%5Crfloor%29%20&plus;%20n) is O(n). Show that the solution
of this recurrence is also Ω(n). Conclude that the solution is Θ(nlgn).
### Answer.
Let us first assume that T(n) >= cnlgn  
![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3E%3D%202c%5Clfloor%20n/2%20%5Crfloor%20lg%28%5Clfloor%20n/2%20%5Crfloor%29%20&plus;%20n%5C%5C%20%5Chspace*%7B1.5cm%7D%3E%3D%202c%28n/2%20-%201%29lg%28n/2%20-1%29%20&plus;%20n%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%20c%28n-2%29%28lg%28n-2%29%20-%20lg2%29%20&plus;%20n%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%20c%28n-1%29lg%28n-1%29%20-%20n%28c-1%29%20&plus;%20c)  
which is inconsistent with induction proof so lets assume that T(n) >= c(n+2)lg(n+2)  
![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3E%3D%202c%5Clfloor%20n/2%20&plus;%202%5Crfloor%20lg%28%5Clfloor%20n/2%20&plus;%202%20%5Crfloor%29%20&plus;%20n%5C%5C%20%5Chspace*%7B1.5cm%7D%3E%3D%202c%28n/2%20&plus;%201%29lg%28n/2%20&plus;%201%29%20&plus;%20n%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%20c%28n&plus;2%29%28lg%28n&plus;2%29%20-%20lg2%29%20&plus;%20n%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%20c%28n&plus;2%29lg%28n&plus;2%29%20-%20n%28c-1%29%20&plus;%20c%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3E%3D%20c%28n&plus;2%29lg%28n&plus;2%29)  
which is true for c <= 1.
### `Exercise 4.3-4`
***
Show that by making a different inductive hypothesis, we can overcome the difficulty
with the boundary condition T(1) = ` for recurrence (4.19) without adjusting
the boundary conditions for the inductive proof.
### Answer.
Given equation is ![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3D%202T%28%5Clfloor%20n/2%20%5Crfloor%29%20&plus;%20n)  
and its solution is given by **_nlgn_**.  
For base case n = 1 it will become 0 but it needs to be 1 , T(1) = 1.  
So we will assume different solution than this, So assume that  
    
    T(n) <= cnlgn + 1
         <= 2 * ((cn/2) * lg(n/2) + 1) + n (putting in equation)
         =  cnlg(n/2) + 2 + n
         = cnlgn - cn + 2 + n
         = cnlgn + 2 -n(c - 1)
         <= cnlgn + 1 + 1 - n(c-1)
         <= cnglgn + 1 
for all c >= 2, Hence proved.
### `Exercise 4.3-5`
***
Show that Θ(nlgn) is the solution to the “exact” recurrence (4.3) for merge sort.
### Answer.
Recurrence is given by  
![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3D%20T%28%5Clceil%20n/2%20%5Crceil%29%20&plus;%20T%28%5Clfloor%20n/2%20%5Crfloor%29%20&plus;%20%5Ctheta%28n%29)  
To prove upper bound we will assume  

        T(n) <= c(n+2)lg(n+2)
and to prove lowe bound we will assume  
    
        T(n) >= c(n+2)lg(n+2)
Rest is same as exercise 4.3-3.
### `Exercise 4.3-6`
***
Show that the solution to ![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3D%202T%28%5Clfloor%20n/2%20%5Crfloor%20&plus;%2017%29%20&plus;%20n)  is O(nlgn).  
### Answer.

Lets assume that 
    
    T(n) <= c(n-a)lg(n-a)
So putting value in equation
    
    T(n) <= 2c(n/2 + 17 - a)lg(n/2 + 17 - a) + n
    T(n) <= c(n + 34 - 2a)lg((n + 34 - 2a)/2) + n
    T(n) <= c(n + 34 - 2a)lg(n + 24 - 2a) - c(n + 34 - 2a) + n
    T(n) <= c(n + 34 - 2a)lg(n + 24 - 2a)
    T(n) <= c(n - a)lg(n - a) for a >= 34
Hence proved.
### `Exercise 4.3-7`
***
Using the master method in Section 4.5, you can show that the solution to the
recurrence ![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3D%204T%28n/3%29%20&plus;%20n%20%5Ctext%7B%20is%20%7D%20T%28n%29%20%3D%20%5Ctheta%28n%5E%7Blog_34%7D%29). Show that a substitution
proof with the assumption ![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3C%3D%20cn%5E%7Blog_34%7D) fails. Then show how to subtract off a
lower-order term to make a substitution proof work.
### Answer.
Assume that  
    ![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3C%3D%20cn%5E%7Blog_34%7D)  
Now using above equation  
![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3C%3D%204c%28n/3%29%5E%7Blog_34%7D%20&plus;%20n%20%5C%5C%20%5Chspace*%7B1.8cm%7D%20%3D%20%5Cdfrac%7B4cn%5E%7Blog_34%7D%7D%7B3%5E%7Blog_34%7D%7D%20&plus;%20n%5C%5C%20%5Chspace*%7B1.8cm%7D%20%3D%20%5Cdfrac%7B4cn%5E%7Blog_34%7D%7D%7B4%5E%7Blog_33%7D%7D%20&plus;%20n%5C%5C%20%5Chspace*%7B1.8cm%7D%20%3D%20%5Cdfrac%7B4cn%5E%7Blog_34%7D%7D%7B4%7D%20&plus;%20n%5C%5C%20%5Chspace*%7B1.8cm%7D%20%3D%20cn%5E%7Blog_34%7D%20&plus;%20n)  
Which clearly not indicate required proof as n is greater than n^log4  
Now assume that  
![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3C%3D%20cn%5E%7Blog_34%7D%20-%203n)  
Putting this into equation  
![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3C%3D%204%28c%28n/3%29%5E%7Blog_34%7D%20-%20n%29%20&plus;%20n%20%5C%5C%20%5Chspace*%7B1.8cm%7D%20%3D%20%5Cdfrac%7B4cn%5E%7Blog_34%7D%7D%7B3%5E%7Blog_34%7D%7D%20-%204n%20&plus;%20n%5C%5C%20%5Chspace*%7B1.8cm%7D%20%3D%20%5Cdfrac%7B4cn%5E%7Blog_34%7D%7D%7B4%5E%7Blog_33%7D%7D%20-%203n%5C%5C%20%5Chspace*%7B1.8cm%7D%20%3D%20%5Cdfrac%7B4cn%5E%7Blog_34%7D%7D%7B4%7D%20-%203n%5C%5C%20%5Chspace*%7B1.8cm%7D%20%3D%20cn%5E%7Blog_34%7D%20-%203n)  
Hence proved.
### `Exercise 4.3-8`
***
Using the master method in Section 4.5, you can show that the solution to the
recurrence T(n) = 4T(n/2) + n^2 is T(n) = Θ(n^2). Show that a substitution
proof with the assumption T(n) <= cn^2 fails. Then show how to subtract off a
lower-order term to make a substitution proof work.
### Answer.
Assume that following holds  
    
    T(n) <= cn^2
Then putting it into equation  
    
    T(n) <= 4c(n/2)^2 + n^2
    T(n) <= cn^2 + n^2
Which clearly does not follow required assumption so now assuming  
    
    T(n) <= cn^2 - n^2
So putting it into equation  
    
    T(n) <= 4( c(n/2)^2 - n
    




