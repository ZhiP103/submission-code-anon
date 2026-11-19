# Algorithm S2. Plot-level plant height from a canopy height model

```text
INPUT:  full-field LAS point cloud (one per flight campaign) ; plot boundary
        shapefile with a plot-ID field ; grid cell size Delta ; vegetation
        threshold tau ; percentile bounds p_lo and p_hi
OUTPUT: one table per campaign giving plant height PH for each plot

1  build a regular orthogonal grid over the extent of the LAS header with cell size Delta
2  if the LAS carries ASPRS classification and ground points (class 2) exceed ratio rho_min of all points
3      ground <- points with class 2
4  else
5      candidate <- the lowest point of every grid cell
6      ground <- candidate points whose local surface normal deviates from the vertical by at most theta
7  DTM <- per-cell minimum elevation of ground points
8  fill empty DTM cells by linear interpolation over the cell centres
9  DSM <- per-cell maximum elevation of all points
10 fill empty DSM cells by linear interpolation over the cell centres
11 CHM <- max(DSM - DTM, 0)
12 for each plot polygon in the shapefile
13     select grid cells whose centres lie inside the polygon
14     vegetation pixels <- selected cells with CHM > tau
15     if no vegetation pixel exists then record PH as missing and continue
16     PH <- mean of CHM values lying within the [p_lo, p_hi] percentile range of the vegetation pixels
17     record (plot ID, PH, number of vegetation pixels, maximum CHM)
18 write the records of all plots of the campaign to a table
```
