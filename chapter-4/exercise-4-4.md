### `Exercise 4.4-1`
***
Use a recursion tree to determine a good asymptotic upper bound on the recurrence
T(n) = 3T(n/2) + n. Use the substitution method to verify your answer.
### Answer.
Using recursion tree we can see that equation will become  
![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3D%20cn%20&plus;%20%5Cdfrac%7B3%7D%7B2%7Dcn%20&plus;%20%5CBig%28%5Cdfrac%7B3%7D%7B2%7D%5CBig%29%5E2cn%20&plus;%20...%20&plus;%20%5CBig%28%5Cdfrac%7B3%7D%7B2%7D%5CBig%29%5E%7Blgn-1%7Dcn%20&plus;%20%5Ctheta%28n%5E%7Blg3%7D%29%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%5Csum_%7Bi%3D0%7D%5E%7Blgn-1%7D%5CBig%28%5Cdfrac%7B3%7D%7B2%7D%5CBig%29%5Eicn%20&plus;%20%5Ctheta%28n%5E%7Blg3%7D%29)  
Being sloppy and using infinite increasing geometric series as upper bound
![equation](http://latex.codecogs.com/gif.latex?%3C%5Csum_%7Bi%3D0%7D%5E%7B%5Cinfty%7D%5CBig%28%5Cdfrac%7B3%7D%7B2%7D%5CBig%29%5Eicn%20&plus;%20%5Ctheta%28n%5E%7Blg3%7D%29%20%3D%20%5Cdfrac%7B1%7D%7B3/2%20-%201%7Dcn%20&plus;%20%5Ctheta%28n%5E%7Blg3%7D%29%20%3D%202cn%20&plus;%20%5Ctheta%28n%5E%7Blg3%7D%29%20%3D%20O%28n%5E%7Blg3%7D%29)  
Thus we have dervied a guess of  
![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3D%20O%28n%5E%7Blg3%7D%29)  
Now using substitution method to verify it assume that  
![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3C%3D%20cn%5E%7Blg3%7D%20-%202n)  
Putting it into equation  
![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3C%3D%203%28c%28n/2%29%5E%7Blg3%7D%20-%20n%29%20&plus;%20n%5C%5C%20%5Chspace*%7B1.82cm%7D%3D%203cn%5E%7Blg3%7D/2%5E%7Blg3%7D%20-%202n%5C%5C%20%5Chspace*%7B1.82cm%7D%3D%20cn%5E%7Blg3%7D%20-%202n%5C%5C)  
Hence proved.  
### `Exercise 4.4-2`
***
Use a recursion tree to determine a good asymptotic upper bound on the recurrence
T(n) = T(n/2) + n^2. Use the substitution method to verify your answer.
### Answer.
Using recursion tree we can see the what equation will become and using same sloopiness as before  
![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3D%20cn%5E2%20&plus;%20cn%5E2/2%20&plus;%20cn%5E2/2%5E2%20&plus;%20...%20&plus;%20cn%5E2/2%5E%7Blgn-1%7D%20&plus;%20%5Ctheta%28n%29%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%5Csum_%7Bi%3D0%7D%5E%7B%5Cinfty%7Dcn%5E2/2%5Ei%20&plus;%20%5Ctheta%28n%29%5C%5C%20%5Chspace*%7B1.5cm%7D%3Dcn%5E2%5Cdfrac%7B1%7D%7B2-1%7D%20&plus;%20%5Ctheta%28n%29%5C%5C%20%5Chspace*%7B1.5cm%7D%3Dcn%5E2%20&plus;%20%5Ctheta%28n%29%5C%5C%20%5Chspace*%7B1.5cm%7D%3DO%28n%5E2%29)  

Now using substitution method to proof it assume that 
    
    T(n) <= cn^2
Putting it into equation  
![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3C%3D%20c%28n/2%29%5E2%20&plus;%20n%5E2%5C%5C%20%5Chspace*%7B1.5cm%7D%3Dcn%5E2/4%20&plus;%20n%5E2%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%28c/4%20&plus;%201%29n%5E2%5C%5C%20%5Chspace*%7B1.5cm%7D%3C%3D%20O%28n%5E2%29)  
Hence proved.
### `Exercise 4.4-3`
***
Use a recursion tree to determine a good asymptotic upper bound on the recurrence
T(n) = 4T(n/2 + 2) + n. Use the substitution method to verify your answer.
### Answer.
Using recursion tree we can see the equation will become  
![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%3D%20%5Csum_%7Bi%20%3D%200%7D%5E%7B%5Clg%20n%7D%204%5Ei%20%5Ccdot%20c%5Cleft%28%5Cfrac%20n%20%7B2%5Ei%7D%20&plus;%202%5Cright%29%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%20%5Csum_%7Bi%20%3D%200%7D%5E%7B%5Clg%20n%7D%204%5Ei%20%5Ccdot%20c%5Cfrac%20n%20%7B2%5Ei%7D%20&plus;%20%5Csum_%7Bi%20%3D%200%7D%5E%7B%5Clg%20n%7D%204%5Ei%20%5Ccdot%20c%20%5Ccdot%202%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%20cn%20%5Csum_%7Bi%20%3D%200%7D%5E%7B%5Clg%20n%7D%20%5Cfrac%20%7B4%5Ei%7D%20%7B2%5Ei%7D%20&plus;%202c%20%5Csum_%7Bi%20%3D%200%7D%5E%7B%5Clg%20n%7D%204%5Ei%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%20cn%20%5Csum_%7Bi%20%3D%200%7D%5E%7B%5Clg%20n%7D%202%5Ei%20&plus;%202c%20%5Csum_%7Bi%20%3D%200%7D%5E%7B%5Clg%20n%7D%204%5Ei%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%20cn%20%5Cfrac%20%7B2%5E%7B%5Clg%20n%20&plus;%201%7D%20-%201%7D%20%7B2%20-%201%7D%20&plus;%202c%20%5Cfrac%20%7B4%5E%7B%5Clg%20n%20&plus;%201%7D%20-%201%7D%20%7B4%20-%201%7D%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%20cn%20%282%5E%7B%5Clg%20n%20&plus;%201%7D%20-%201%29%20&plus;%20%5Cfrac%20%7B2c%7D%203%20%284%5E%7B%5Clg%20n%20&plus;%201%7D%20-%201%29%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%20cn%20%282%20%5Ccdot%202%5E%7B%5Clg%20n%7D%20-%201%29%20&plus;%20%5Cfrac%20%7B2c%7D%203%20%284%20%5Ccdot%204%5E%7B%5Clg%20n%7D%20-%201%29%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%20cn%20%282%20%5Ccdot%20n%20-%201%29%20&plus;%20%5Cfrac%20%7B2c%7D%203%20%284%20%5Ccdot%20n%5E2%20-%201%29%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%202cn%5E2%20-%202n%20&plus;%20%5Cfrac%20%7B8cn%5E2%7D%203%20-%20%5Cfrac%20%7B2c%7D%203%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%20O%28n%5E2%29)  
Now using substitution method to prove this assume that  
    
    T(n) <= cn^2 - nd

Now putting it into equation  
![equation](http://latex.codecogs.com/gif.latex?T%28n%29%20%5Cle%204%28c%28n/2%20&plus;%202%29%5E2%20-%20dn%29%20&plus;%20n%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%204%28cn%5E2/4%20&plus;%202cn%20&plus;%204c%20-%20dn%29%20&plus;%20n%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%20cn%5E2%20&plus;%208cn%20&plus;%2016c%20-%204dn%20&plus;%20n%20%5C%5C%20%5Chspace*%7B1.5cm%7D%3D%20cn%5E2%20-%20n%284d%20-%208c%20-%201%29%20&plus;%2016c%20%5C%5C%20%5Chspace*%7B1.5cm%7D%5Cle%20d%28n%5E2%20-%20bn%29)  
This is true as long as (4d - 8c + 1) >= 0  
Hence proved.  
### `Exercise 4.4-4`
***
Use a recursion tree to determine a good asymptotic upper bound on the recurrence
T(n) = 2T(n-1) + 1. Use the substitution method to verify your answer.
### Answer.
Using recursion we can see it will become a complete binary tree with 2^i nodes at each level  
![equation](http://latex.codecogs.com/gif.latex?%5Chspace%7B-1.5cm%7DT%28n%29%20%3D%20%5Csum_%7Bi%20%3D%200%7D%5E%7Bn%7D%202%5Ei%20%5Ccdot%201%20%5C%5C%20%3D%20%5Cfrac%20%7B2%5E%7Bn%20&plus;%201%7D%20-%201%7D%20%7B2%20-%201%7D%20%5C%5C%20%3D%202%5E%7Bn%20&plus;%201%7D%20-%201%20%5C%5C%20%3D%202.2%5En%20-%201%20%5C%5C%20%5Cle%20c2%5En%20%5C%5C%20%3D%20O%282%5En%29)  
Now using substitution method to validate it assume that  
    
    T(n) <= c2^n - 1
Now putting it into equation  
![equation](http://latex.codecogs.com/gif.latex?%5Chspace%7B-1.5cm%7DT%28n%29%20%5Cle%202%28c2%5E%7Bn-1%7D-1%29%20&plus;%201%5C%5C%20%3D%20c2%5En%20-%202%20&plus;%201%5C%5C%20%3D%20c2%5En%20-%201)  
Hence proved.  
### `Exercise 4.4-5`
***
Use a recursion tree to determine a good asymptotic upper bound on the recurrence
T(n) = T(n-1) + T(n/2). Use the substitution method to verify your answer.
### Answer.
Not yet done
### `Exercise 4.4-6`
***
Argue that the solution to the recurrence T(n) = T(n/3) + T(2n/3) + cn, where c
is a constant, Ω(nlgn) by appealing to a recursion tree.
### Answer.
We can see that at each level when we sum all the nodes the whole result become cn 
    
    cn                                   = cn (First level)
    cn/3 + 2cn/3 = 3cn/3                 = cn (second level) 
    cn/9 + 2cn/9 + 2cn/9 + 4cn/9 = 9cn/9 = cn (third level)
Also tree will go to the max level of lg_3n and at each level cn work is happening so at least nlgn time complexity is there

    T(n) = Ω(nlgn)

Hence proved

### `Exercise 4.4-7`
***
Draw the recursion tree for T(n) = 4T(n/2) + cn, where c is a constant, and
provide a tight asymptotic bound on its solution. Verify your bound by the substitution
method.
### Answer.
We can see from the recursion tree that equation will become  
![equation](http://latex.codecogs.com/gif.latex?%5Chspace%7B-1.5cm%7DT%28n%29%3D%20cn%20%5Ccdot%20%5Csum_%7Bi%20%3D%200%7D%5E%7B%5Clg%20n%7D%202%5Ei%20%5C%5C%20%3D%20cn%20%5Cfrac%20%7B2%5E%7B%5Clg%20n%20&plus;%201%7D%20-%201%7D%20%7B2%20-%201%7D%20%5C%5C%20%3D%20cn%20%282%5Ccdot2%5E%7B%5Clg%20n%7D%20-%201%29%20%5C%5C%20%3D%20cn%20%28%202n%20-%201%29%20%5C%5C%20%3D%202cn%5E2%20-%202cn%20%3D%20O%28n%5E2%29)  
Verifying by substituition method assume that
    
    T(n) <= cn^2 - dn
    
Now putting it into equation  
![equation](http://latex.codecogs.com/gif.latex?%5Chspace%7B-1.5cm%7DT%28n%29%20%3C%3D%204%28c%5Ccdot%20n%5E2/4%20-%20dn%29&plus;%20cn%5C%5C%20%3D%20cn%5E2%20&plus;%20cn%20%5C%5C%20%3D%20cn%5E2%20-%204dn%20&plus;%20cn%5C%5C%20%3D%20cn%5E2%20-%20n%284d%20-c%29%5C%5C%20%3C%3D%20cn%5E2%20-%20nd%27) 
Hence proved.
### `Exercise 4.4-8`
***
Use a recursion tree to give an asymptotically tight solution to the recurrence
T(n) = T(n-a) + T(a) + cn, where a >= 1 and c > 0 are constants.
### Answer.
We can see from the recursion that the equation will become  
![equation](http://latex.codecogs.com/gif.latex?%5Chspace%7B-0.3cm%7D%5Csum_%7Bi%3D0%7D%5E%7Bn/a%20-%201%7D%20c%28n-ia%29%20&plus;%20T%28a%29%5C%5C%20%3D%5Csum_%7Bi%3D0%7D%5E%7Bn/a%20-%201%7Dcn%20-%20%5Csum_%7Bi%3D0%7D%5E%7Bn/a%20-%201%7Dica%20&plus;%20%5Csum_%7Bi%3D0%7D%5E%7Bn/a%20-%201%7DT%28a%29%5C%5C%20%3Dcn.n/a%20-%20ca%28n/a%20.%20%28n/a%20-1%29%29%29/2%20&plus;%20T%28a%29.n/a%5C%5C%20%3D%20cn%5E2/a%20-%20c.%28n%5E2/a%20-%20n%29/2%20&plus;%20T%28a%29.n/a%5C%5C%20%3D%20cn%5E2/a%20&plus;%20%28c%20&plus;%20T%28a%29/a%29.n%5C%5C%20%3D%20%5Ctheta%20%28n%5E2%29)  
### `Exercise 4.4-9`
***
Use a recursion tree to give an asymptotically tight solution to the recurrence
T(n) = T(nα) + T((1 - α)n) + cn, where α is a constant in the range 0 < α < 1
and c > 0 is also a constant.
### Answer.
Since the sum of both childs

    nα + (1-α)n
    nα + n - αn
    n
Hence the solution will be nlgn







