# Python Slicing Operator
```
>>> x[:]                # [x[0],   x[1],          ..., x[-1]    ]
>>> x[low:]             # [x[low], x[low+1],      ..., x[-1]    ]
>>> x[:high]            # [x[0],   x[1],          ..., x[high-1]]
>>> x[low:high]         # [x[low], x[low+1],      ..., x[high-1]]
>>> x[::stride]         # [x[0],   x[stride],     ..., x[-1]    ]
>>> x[low::stride]      # [x[low], x[low+stride], ..., x[-1]    ]
>>> x[:high:stride]     # [x[0],   x[stride],     ..., x[high-1]]
>>> x[low:high:stride]  # [x[low], x[low+stride], ..., x[high-1]]

```
