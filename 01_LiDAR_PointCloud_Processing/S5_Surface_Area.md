# Algorithm S5. Canopy surface area from exposed voxel facets

```text
INPUT:  normalized plot point cloud ; voxel edge Delta
OUTPUT: canopy surface area A of the plot

1  build the voxel grid with edge Delta and obtain the occupied voxel set after occlusion filling
2  exposed <- 0
3  for each occupied voxel
4      for each of the six orthogonal directions (+x, -x, +y, -y, +z, -z)
5          if the neighbouring voxel in that direction is not occupied
6              exposed <- exposed + 1
7  A <- exposed times Delta squared
8  return A
```
