# Algorithm S10. Extraction of dynamic attributes

```
function extract(f*, x, y, popt)
1  dy <- first derivative of f* with respect to x
2  on the rising part of the curve: A <- x where dy reaches its maximum
3  C <- that rate ;  B <- f*(A)
4  D <- x where f* reaches its maximum ;  E <- f*(D)
5  if A or D lies outside the sampling window
6      A, B, C, D, E <- re-evaluated on a dense grid inside the window
7  if A or D lies close to the window edge, or the maximum rate is not positive
8      flag <- boundary
9  return (A, B, C, D, E, flag)
```
