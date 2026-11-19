# Algorithm S1. Plot-wise segmentation of the LiDAR point cloud

```text
INPUT:  LAS files (one per flight campaign) ; plot boundary shapefiles (LN and NN sets,
        with a plot-ID field) ; target projected CRS ; minimum point count N_min ;
        sampling ratio r for the overview map
OUTPUT: one PLY point cloud per plot ; one overlay image per shapefile

1  for each LAS file L in the campaign folder
2      P <- read_las(L)                                      # N x 3 coordinates (x, y, z)
3      for each boundary set B in {LN, NN}
4          S <- open_shapefile(B)
5          if CRS(S) is not the target CRS
6              S <- transform_geometry(S, target CRS)
7          polys, ids, tags <- empty
8          for each feature F in S
9              id <- field(F, 'Id') ; if id is empty then id <- feature index of F
10             id <- sanitize(id)
11             if geometry(F) is a Polygon
12                 append polys, ids, tags with (polygon, id, '')
13             else if geometry(F) is a MultiPolygon
14                 for each part k of geometry(F)
15                     append polys, ids, tags with (part, id, '_' + k)
16         index <- build_spatial_index(polys)
17         plot_overlay(P, polys, ids, tags, sampling ratio = r) -> overview image for B
18         for each (poly, id, tag) in (polys, ids, tags)
19             C <- points of P inside bounding_box(poly)
20             C <- points of C inside exterior ring of poly
21             if poly has interior rings
22                 C <- points of C not inside any interior ring
23             if number of points in C < N_min
24                 record (id + tag) as skipped ; continue
25             write_ply(C) -> <prefix>_<id><tag>.ply
26         end for
27     end for
28 end for

function plot_overlay(P, polys, ids, tags, r)
1  if number of points in P exceeds 200000
2      P <- random sample of P with fraction r, fixed seed
3  draw P as a scatter layer
4  for each (poly, id) in (polys, ids)
5      draw boundary of poly as an outline
6      write id at the centroid of poly
7  set axis limits to the extent of P expanded by a margin
8  save image to disk
```
