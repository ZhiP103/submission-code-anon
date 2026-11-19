# Algorithm S1. Main procedure

```
INPUT:  X (predictor traits), y (biomass), K (number of folds), α (hold-out proportion)
OUTPUT: cross-validation metrics (mean ± SD), hold-out metrics, fitted models

1  (X, y) <- load_and_prepare(data)
2  label_i <- nitrogen treatment of sample i
3  (X_dev, y_dev), (X_hold, y_hold) <- stratified_split(X, y, test_size = α, stratify = NN / LN)
4  for each model M in {Linear Regression, Random Tree, Random Forest, XGBoost}
5      (metrics_M, model_M) <- train(M, X_dev, y_dev, K)
6      ŷ_hold <- predict(model_M, X_hold)
7      holdout_M <- evaluate(y_hold, ŷ_hold)
8      record metrics_M and holdout_M
9  end for
10 select the model with the highest mean cross-validated R²
11 report the hold-out metrics of that model as the final result
12 save fitted models
```
