# Algorithm S3. Spatial porosity from dual-scale voxel grids

```text
INPUT:  normalized plot point cloud ; coarse voxel size Delta_c ; fine voxel size Delta_f
OUTPUT: spatial porosity phi of the plot

1  for each scale Delta in {Delta_c, Delta_f}
2      build an orthogonal voxel grid over the bounding box of the point cloud with edge Delta
3      mark a voxel as occupied when it contains at least one point
4      V(Delta) <- number of occupied voxels times Delta cubed
5  phi <- 1 - V(Delta_f) / V(Delta_c)
6  return phi
```
