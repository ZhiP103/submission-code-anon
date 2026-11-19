# Algorithm S6. XGBoost with nested hyperparameter tuning

```
INPUT:  X, y, K ;  search space Θ ;  T, n_inner, β, E, n_min
        Θ = {depth, learning rate, subsample ratio, column sample ratio,
             minimum loss reduction, L1 and L2 regularization, minimum child weight}
OUTPUT: fold metrics (mean ± SD), final model

function tune(X_tr, y_tr)
1  (X_sub, y_sub), (X_val, y_val) <- split(X_tr, y_tr, test_size = β)
2  search <- random search over Θ (n_iter = T,
                                  cv = n_inner-fold, shuffled,
                                  scoring = R²).fit(X_sub, y_sub)
3  probe <- XGBoost(search.best_params).fit(X_sub, y_sub,
                                           eval_set = [(X_val, y_val)],
                                           early_stopping = E)
4  n <- max(probe.best_iteration + 1, n_min)
5  return (search.best_params, n)

function train_xgb(X, y, K)
1  folds <- K-fold partition of (X, y), K folds, shuffled, seed = SEED
2  for each (train, valid) in folds
3      X_tr, y_tr <- X[train], y[train]
4      X_va, y_va <- X[valid], y[valid]
5      (θ_f, n_f) <- tune(X_tr, y_tr)
6      m <- XGBoost(θ_f, rounds = n_f).fit(X_tr, y_tr)
7      ŷ_tr <- m.predict(X_tr) ;  ŷ_va <- m.predict(X_va)
8      errors_tr <- evaluate(y_tr, ŷ_tr) ;  errors_va <- evaluate(y_va, ŷ_va)
9      record errors_tr, errors_va, ŷ_va and (θ_f, n_f)
10 end for
11 θ_final <- most frequent θ over the folds ;  n_final <- median n over the folds
12 final <- XGBoost(θ_final, rounds = n_final).fit(X, y)
13 return (mean ± SD of fold metrics, final)
```
