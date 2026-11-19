# Algorithm S4. Canopy volume from occluded voxel reconstruction

```text
INPUT:  normalized plot point cloud ; voxel edge Delta
OUTPUT: canopy volume V of the plot

1  build an orthogonal voxel grid over the bounding box of the point cloud with edge Delta
2  mark a voxel as occupied when it contains at least one point
3  for each horizontal column (fixed x, y)
4      find the uppermost occupied voxel in that column
5      if such a voxel exists
6          mark every voxel of the column lying below it as occupied
7  V <- number of occupied voxels after filling times Delta cubed
8  return V
```
