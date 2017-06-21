# Lesson2
**When calcualting path in a matrix, the ```f[0][0]``` should equal to
```1``` since the element already exist. However in sequence the first
element commonly does not exist in the problem set, so ```f[0]``` should
equal to ```0```** (Robot question VS. Paint house)

## Memory Optimization
Reuse the rows in matrix that does not matter anymore since we are only
returning the last value of the entire calculation.

