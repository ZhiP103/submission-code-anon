# Algorithm S5. Random Forest (RF)

```
INPUT:  X, y, K ;  fixed hyperparameters θ_RF (number of trees, depth, minimum samples
        to split, minimum samples per leaf, traits per split, seed)
OUTPUT: fold metrics (mean ± SD), final model

1  folds <- K-fold partition of (X, y), K folds, shuffled, seed = SEED
2  for each (train, valid) in folds
3      X_tr, y_tr <- X[train], y[train]
4      X_va, y_va <- X[valid], y[valid]
5      m <- random forest(θ_RF).fit(X_tr, y_tr)
6      ŷ_tr <- m.predict(X_tr) ;  ŷ_va <- m.predict(X_va)
7      errors_tr <- evaluate(y_tr, ŷ_tr) ;  errors_va <- evaluate(y_va, ŷ_va)
8      record errors_tr, errors_va and ŷ_va
9  end for
10 final <- random forest(θ_RF).fit(X, y)
11 return (mean ± SD of fold metrics, final)
```
