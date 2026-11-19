# Algorithm S3. Gaussian function

```
INPUT:  x, y
OUTPUT: parameters (a, b, c), or failure

1  a <- maximum of the observed series ;  b <- date of the observed maximum
2  c <- one quarter of the sampled span
3  model: y(x) = a * exp( -(x - b)^2 / (2 c^2) )
4  popt <- nonlinear least squares( model, x, y, initial = (a, b, c) )
5  constraints: a >= 0, b >= 0, c >= 1
6  return popt, or report a failure
```
