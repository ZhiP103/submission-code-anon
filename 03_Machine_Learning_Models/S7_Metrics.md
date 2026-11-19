# Algorithm S7. Evaluation metrics

```
function evaluate(y_true, ŷ)
1  RMSE  <- sqrt( mean( (ŷ - y_true)^2 ) )
2  R²    <- 1 - Σ( ŷ - y_true )^2 / Σ( y_true - mean(y_true) )^2
3  NRMSE <- RMSE / mean( |y_true| )
4  return (R², RMSE, NRMSE)
```
