# Lesson1
## Intro of DP
E.G. Robot is on the topleft corner of a matrix. Can only walk right and
downwards?
### When to use DP?
* How many ways to do something?  
* MAX and MIN  
* Existance  

### Four principles
* confirm state
  * What is the element in the Array/Matrix

### Problem 1
Three type of coins, $2, $5 and $7, how many ways to get $27? Follow up
min number coins usage to get $27?  

Assume:  
the min amount of coin usage is ```k```  
Last coin is ```ak```  
The rest is ``` 27 - ak```  

Since assuming this is the min amount of usage. ```27 - ak``` uses the
min amount of coins as well, aka ```k-1```.  

Then this is a sub problem of the original problem and the sub problem
is a smaller scale of the original problem.  

Assume the original problem is ```f(x)``` which is the min amount of coins to
get ```x```. Then we have: ```f(27) = min{f(27-2) + 1, f(27-5) + 1,
f(27-7) + 1}```  

```
function f(x) {
  if(x == 0) return 0;
  res = MAX_VALUE;
  ...
}
```

Use and Array ```f[27] = min{f[27-2] + 1, f[27-5] + 1,
f[27-7] + 1}```  

Array boundary: Any ```x < 0 f[x] = +infinite```  
Base case: ```f[0] = 0```  
Calculation start from smaller number to larger number.  

### Problem 2
E.G. Robot is on the topleft corner of a matrix. Can only walk right and
downwards. How many ways to get to the bottom right corner?

Last Step has to come from the top or from the left.  
Assume there are ```f[m][n]``` ways to get to bottom left.  
f[m][n] = f[m-1][n] + f[m][n-1]  
Base case: f[0][0] = 1  

For 2D DP we calculate the elements from the first row and then go to
bottom.  

Time Complexity = O(m*n)  
Space Complexity = O(m*n)

### Problem 3
Jump Game:
There are n stones in a array. A frog is on the first stone want to get
to n-1 stone. If the frog at the i position the frog can jump a[i]
steps.  

Two things needs to happen. Frog can jump to stone i. And last step has
to get to stone n-1.  

** Sub problem ** weather the frog can jump to stone i.  
Assume: ```f[j]``` is weather the frog can jump to stone i.  

Base case: ```f[0] = true```

