# Algorithm S7. Plot-level indicator summary

```text
INPUT:  folders of normalized plot point clouds, one folder per flight campaign ;
        plant height table of each campaign ; point-count threshold for subsampling ;
        flush size N_f
OUTPUT: one CSV file per campaign listing plot ID and the extracted indicators

1  for each campaign folder
2      load the plant height table of the campaign, indexed by plot ID
3      open the campaign CSV and write the header row
4      for each plot point cloud in the folder
5          n <- point count read from the file header
6          if the file exceeds the size threshold
7              keep a uniformly random subsample of the points at the target fraction
8              replace the working file by the subsampled one
9          if n equals zero then skip the plot
10         PH  <- plant height of this plot ID from the table
11         phi <- porosity by Algorithm S3
12         V   <- canopy volume by Algorithm S4
13         A   <- canopy surface area by Algorithm S5
14         A_xy <- vertical projected area by Algorithm S6
15         append the row (file name, n, PH, phi, V, A, A_xy)
16         if the number of buffered rows reaches N_f then write them and clear the buffer
17     write the remaining buffered rows
```
