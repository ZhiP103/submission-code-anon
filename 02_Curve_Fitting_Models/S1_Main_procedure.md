# Algorithm S1. Main procedure

```
INPUT:  growth table (one row per curve, one column per sampling date)

1  (ids, x, Y) <- prepare(table)
2  for each function f in {Gaussian, Weibull, Linear, Polynomial, Fourier}
3      for each curve i
4          popt_if <- fit(f, x, y_i)
5          if popt_if is empty
6              record the failure of curve i under f ; continue
7          metrics_if <- evaluate(f, x, y_i, popt_if)
8      end for
9      summary_f <- mean of metrics_if over all curves
10 end for
11 f* <- select_function(summary)
12 for each curve i
13     (A_i, B_i, C_i, D_i, E_i, flag_i) <- extract(f*, x, y_i, popt_i)
14 save parameter tables, metric tables, figures and attributes
```
