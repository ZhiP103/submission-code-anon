# Algorithm S4. Weibull function

```
INPUT:  x, y
OUTPUT: parameters (K, lambda, k), or failure

1  K <- observed maximum, slightly above ;  lambda <- median of x ;  k <- 2
2  model: y(x) = K * (1 - exp( -(x / lambda)^k ))
3  popt <- nonlinear least squares( model, x, y, initial = (K, lambda, k) )
4  constraints: K > 0, lambda > 0, k > 0
5  return popt, or report a failure
```
