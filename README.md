# Python Slicing Operator

A. Preprocessing
1. Data
```
>>> x = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
>>> l = len(x) 
# l = 10
```
2. Positive indexing
```
# x[0] = 1, x[1] = 2, x[2] = 3, x[3] = 4, x[4] = 5, x[5] = 6
# x[6] = 7, x[7] = 8, x[8] = 9, x[9] = 10
# x[0] ... x[l-1]
```
3. Negative indexing
```
# x[-1] = 10, x[-2] = 9, x[-3] = 8, x[-4] = 7, x[-5] = 6, x[-6] = 5
# x[-7] = 4, x[-8] = 3, x[-9] = 2, x[-10] = 1
# x[-1] ... x[-l]
```
4. Deriving one from another
```
p = positive index
n = negative index
p - n = l
p = l + n
n = -l + p
p =[0, ..., l-1]
n =[-l, ..., -1]
```

B. Positive stride

1. General
```
>>> x[low:high:stride]
# low to high, element at index low included, 
# then next is obtained by adding the step stride to the previous element
# element at index high is excluded
# if the last jump falls to the index high-1, element at index high-1 is included
# if the last jump does not fall to the index high-1, element at index high-1 is excluded
# [x[low], x[low+stride], ..., x[last]], last <= high-1
# low < high, if one of the index is negative add the length l to it 
# then comparing it with positive indices
# if low >= high, ==> []
```
2. Stride is 1

a. General
```
>>> x[low:high:1]
>>> x[low:high]        
# [x[low], x[low+1],      ..., x[high-1]]
# low to high, element at index low included, element at index high excluded
```
b. Full bounds
```
>>> x[0:l:1]
>>> x[0:l]
>>> x[:] 
>>> x[::1] 
>>> x[::] 
# 0 to l, element at index 0 included, element at index l excluded
# [x[0] ... x[l-1]]
# [x[0],   x[1],          ..., x[-1]]
# [x[-l] ... x[l-1]]
```
c. Lower bound restricted, upper bound is maximum
```
>>> x[low:]
>>> x[low::]
 # low to l, element at index low included, element at index l excluded
 # [x[low], x[low+1],      ..., x[l-1]]
 # [x[low], x[low+1],      ..., x[-1]]
 ```
d. Upper bound restricted, lower bound is minimum
```
>>> x[:high] 
# 0 to high, element at index 0 included, element at index high excluded
# [x[0],   x[1],          ..., x[high-1]]
# [x[-l],   x[-l+1],          ..., x[high-1]]
```
3. Stride is more than 1, stride >= 1

a. Lower bound restricted, upper bound is maximum
```
>>> x[low::stride]  
# x[low:l:stride]  
# [x[low], x[low+stride], ..., x[last]], last <= l-1
```
b. Upper bound restricted, lower bound is minimum
```
>>> x[:high:stride]
# x[0:high:stride]  
# [x[0],   x[0+stride],     ..., x[last]], last <= high-1
```

C. Negative stride

1. General
```
>>> x[high:low:-stride]
# high to low, element at index high included, 
# then next is obtained by substracting the step stride to the previous element
# element at index low is excluded
# if the last jump falls to the index low+1, element at index low+1 is included
# if the last jump does not fall to the index low+1, element at index low+1 is excluded
# [x[high], x[high-stride], ..., x[last]], last >= low+1
# high > low, if one of the index is negative add the length l to it 
# then comparing it with positive indices
# if high <= low, ==> []
```
2. Stride is 1

a. General
```
>>> x[high:low:-1]      
# [x[high], x[high-1],      ..., x[last]], last >= low+1
# high to low, element at index high included, element at index low excluded
```
b. Full bounds 
```
>>> x[l-1:-l-1:-1]
>>> x[-1:-l-1:-1]
>>> x[::-1] 
# l-1 to -l-1, element at index l-1 included, element at index -l-1 excluded
# index -l-1 comes after the first element which has index 0, or -l
# -l-100, -l-99, ..., -l-1, -l-0, -l+1, ..., -1
# [x[l-1] ... x[0]
# [x[-1],   x[-1-1],          ..., x[-l]]
```
c. Upper bound restricted, lower bound is minimum
```
>>> x[high::-1]  
 # high to -l-1, element at index high included, element at index -l-1 excluded
 # [x[high], x[high-1],      ..., x[-l]]
 # [x[high], x[high-1],      ..., x[0]]
 ```
 c. Lower bound restricted, lower bound is minimum
 ```
>>> x[:low:-1] 
# -1 to low, element at index -1 included, element at index low excluded
# [x[-1],   x[-1-1],          ..., x[low+1]]
```
3. Stride is more than 1, stride >= 1

a. Upper bound restricted, lower bound is minimum
```
>>> x[high::stride]  
# x[high:-l-1:stride]  
# [x[high], x[high-stride], ..., x[last]], last <= 0, or -l
```
b. Lower bound restricted, upper bound is maximum
```
>>> x[:low:stride]
# x[-1:low:stride]  
# [x[-1],   x[-1-stride],     ..., x[last]], last >= low+1
```
