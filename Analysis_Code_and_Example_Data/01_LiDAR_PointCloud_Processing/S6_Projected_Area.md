# Algorithm S6. Vertical projected area from orthogonal voxel projection

```text
INPUT:  normalized plot point cloud ; voxel edge Delta
OUTPUT: vertical projected area A_xy of the plot

1  build the voxel grid with edge Delta and obtain the occupied voxel set after occlusion filling
2  collect the pair (x index, y index) of every occupied voxel
3  remove duplicated pairs so that each horizontal cell is counted once
4  A_xy <- number of distinct pairs times Delta squared
5  return A_xy
```
