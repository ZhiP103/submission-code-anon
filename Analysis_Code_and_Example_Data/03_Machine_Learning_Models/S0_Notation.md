# Algorithm S0. Notation

| Symbol | Meaning |
|---|---|
| **X** | predictor matrix, one row per sample, p phenotypic traits per row |
| **y** | response vector, ground-measured biomass |
| p | number of predictor traits |
| N | number of samples used for modelling |
| K | number of cross-validation folds |
| α | proportion of samples held out for the final evaluation |
| β | proportion of each training fold used as the inner validation set |
| T | number of candidate hyperparameter sets evaluated in the random search |
| n_inner | number of folds used inside the random search |
| E | early-stopping patience |
| n_min | lower bound on the number of boosting rounds |
| Θ | hyperparameter space of XGBoost |
| θ_M | fixed hyperparameter set of model M (M = LR, RT, RF) |
| SEED | fixed random seed for splitting, fold assignment and model initialization |
| NN / LN | normal-nitrogen / low-nitrogen treatment, used only as the stratification variable of the split |
| ŷ | predicted value |
| R² | coefficient of determination |
| RMSE | root mean square error |
| NRMSE | RMSE normalized by the mean absolute observed value |

Algorithms

```
S1 — main procedure
S2 — data preparation
S3 — Linear Regression (LR)
S4 — Random Tree (RT)
S5 — Random Forest (RF)
S6 — XGBoost with nested hyperparameter tuning
S7 — evaluation metrics
```
