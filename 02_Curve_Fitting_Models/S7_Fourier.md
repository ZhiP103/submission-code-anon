# Algorithm S7. Fourier function

```
INPUT:  x, y
OUTPUT: parameters (a0, a1, b1, a2, b2, w), or failure

1  a0 <- mean of y ;  a1, b1, a2, b2 <- 1 ;  w <- 0.1
2  model: y(x) = a0 + a1 cos(w x) + b1 sin(w x) + a2 cos(2 w x) + b2 sin(2 w x)
3  popt <- nonlinear least squares( model, x, y, initial = (a0, a1, b1, a2, b2, w) )
4  constraints: w in [1e-4, pi/2] ; other parameters unconstrained
5  return popt, or report a failure
```
