# Algorithm S2. Data preparation

```
INPUT:  growth table
OUTPUT: curve identifiers, time axis x, observation matrix Y

1  read the table ; one row per curve, one column per sampling date
2  first column -> curve identifier
3  names of the remaining columns -> time axis x
4  remaining columns -> observation sequence of each curve
5  return (ids, x, Y)
```
