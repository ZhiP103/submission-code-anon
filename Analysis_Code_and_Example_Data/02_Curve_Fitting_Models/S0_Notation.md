# Algorithm S0. Notation

| Symbol | Meaning |
|---|---|
| y(x) | fitted value of the indicator at time x |
| x | days after sowing (DAS) |
| a, b, c | parameters of the Gaussian function: peak value, peak time, peak width |
| K, lambda, k | parameters of the Weibull function: asymptote, characteristic time, shape |
| p | number of parameters of a candidate function |
| n | number of sampling dates in one curve |
| SSE, SST | sum of squares of residuals and of the observed series |
| R² | coefficient of determination, adjusted for the number of parameters |
| RMSE | root mean square error |
| NRMSE | RMSE normalized by the mean absolute observed value |
| Theta_f | parameter constraints of function f |
| f* | the single function selected for the whole study |
| A, B, C, D, E | the five dynamic attributes |

Algorithms

```
S1  — main procedure
S2  — data preparation
S3  — Gaussian function
S4  — Weibull function
S5  — Linear function
S6  — Polynomial function
S7  — Fourier function
S8  — fitting and evaluation metrics
S9  — selection of the single function
S10 — extraction of dynamic attributes
```
