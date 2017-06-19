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



