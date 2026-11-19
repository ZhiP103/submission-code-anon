# Algorithm S8. Visual check of plot-wise height structure

```text
INPUT:  normalized plot point clouds of one flight campaign ; horizontal cell size ;
        lower and upper bounds of the height colour scale
OUTPUT: one top-view height image of the whole campaign

1  merge the point clouds of all plots of the campaign
2  divide the horizontal plane into cells of the given size
3  for each cell keep the maximum height of the points falling inside it
4  map the cell heights to colours using the fixed scale, cells without points left blank
5  draw the coloured grid at the given resolution and save the image to disk
```
