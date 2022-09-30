# Python Slicing Operator
Positive Stride 

>>> x = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
>>> l = len(x) 
# l = 10

# Positive indexing

# x[0] = 1, x[1] = 2, x[2] = 3, x[3] = 4, x[4] = 5, x[5] = 6
# x[6] = 7, x[7] = 8, x[8] = 9, x[9] = 10
# x[0] ... x[l-1]

# Negative indexing
# x[-1] = 10, x[-2] = 9, x[-3] = 8, x[-4] = 7, x[-5] = 6, x[-6] = 5
# x[-7] = 4, x[-8] = 3, x[-9] = 2, x[-10] = 1
# x[-1] ... x[-l]


1. 
a.
>>> x[low:high]        
# [x[low], x[low+1],      ..., x[high-1]]
# `low` to `high`, element at index `low` included, element at index `high` excluded

b. 
>>> x[0:l]
>>> x[:]   
# `0` to `l`, element at index `0` included, element at index `l`excluded
# x[0] ... x[l-1]
# [x[0],   x[1],          ..., x[-1]]
# x[-l] ... x[l-1]

c.
>>> x[low:]  
 # low to `l`, element at index `low` included, element at index `l`excluded
 # [x[low], x[low+1],      ..., x[l-1]
 # [x[low], x[low+1],      ..., x[-1]
 
>>> x[:high] 
# `0` to `high`, element at index `0` included, element at index `high` excluded
# [x[0],   x[1],          ..., x[high-1]]
# [x[-l],   x[-l+1)],          ..., x[high-1]]


2.
a.
>>> x[low:high:stride]
# `low` to `high`, element at index `low` included, 
# then next is obatined by adding the step stride to the previous element
# element at index `high` is excluded
# if the last jump falls to the index `high-1`, element at index `high-1` is included
# if the last jump does not fall to the index `high-1`, element at index `high-1` is excluded
# [x[low], x[low+stride], ..., last], last <=x[high-1]

b.
>>> x[0:l:stride] 
>>> x[::stride]
# `0` to `l`, element at index `0` included, step is `stride`, element at index `l`excluded
# [x[0],   x[0 + stride],     ..., last], last <=x[l-1]


c.
 >>> x[0:l:1] 
 >>> x[::1] 
 >>> x[::]   
 # `0` to `l`, element at index `0` included, step is `1`, element at index `l`excluded
 # x[0],x[0+1], ... x[l-1]
 
d.
 >>> x[low::stride]  
# x[low:l:stride]  
# [x[low], x[low+stride], ..., last], last <=x[l-1]

e.
>>> x[:high:stride]
# x[0:high:stride]  
# [x[0],   x[0+stride],     ..., last], last <=x[high-1]



