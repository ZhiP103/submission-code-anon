# Algorithm S6. Polynomial function

```
INPUT:  x, y
OUTPUT: parameters (a, b, c), or failure

1  a <- 0 ;  b <- slope of the least squares line ;  c <- mean of y
2  model: y(x) = a * x^2 + b * x + c
3  popt <- nonlinear least squares( model, x, y, initial = (a, b, c) )
4  constraints: none
5  return popt, or report a failure
```
