# Algorithm S8. Fitting and evaluation metrics

```
function evaluate(f, x, y, popt)
1  yhat <- f(x, popt)
2  SSE  <- sum( (yhat - y)^2 ) ;  SST <- sum( (y - mean(y))^2 )
3  R2   <- 1 - (SSE / SST) * (n - 1) / (n - p - 1)
4  RMSE <- sqrt( SSE / n )
5  NRMSE <- RMSE / mean( |y| )
6  return (R2, RMSE, NRMSE)
```
