# Algorithm S5. Linear function

```
INPUT:  x, y
OUTPUT: parameters (a, b), or failure

1  (a, b) <- least squares line through the observations
2  model: y(x) = a * x + b
3  popt <- nonlinear least squares( model, x, y, initial = (a, b) )
4  constraints: none
5  return popt, or report a failure
```
