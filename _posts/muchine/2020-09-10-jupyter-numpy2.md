---
title: "AI - Numpy(2)"
excerpt: "numpy"
toc: true
toc_sticky: true
categories: ai
tags: ai
last_modified_at: 2020-09-14T08:17:00-18:00
typora-root-url: ..\..\assets\img\muchine
---

## Numpy



- Numpy 함수



#### reshape

- 행, 열 을 재배치

```python
import numpy as np
arr = np.arange(2,6)
print(arr)
# [2 3 4 5]
arr.reshape(2,2)
# array([[2, 3],
#       [4, 5]])
```

#### ravel

```python
import numpy as np
arr = np.array([[1,2,3],[4,5,6]])
print(arr)
#[ [1 2 3]
#  [4 5 6] ]
arr.ravel()
# array([1, 2, 3, 4, 5, 6])
```

#### indexing

```python
arr = np.arange(1,17,1).reshape(4,4).copy()
# [ [ 1  2  3  4]
#   [ 5  6  7  8]
#   [ 9 10 11 12]
#   [13 14 15 16] ]
print(arr[1,2])
print(arr[1][2])
# 7

print(arr[1:3,:])
#[ [ 5  6  7  8]
#  [ 9 10 11 12] ]

print(arr[1:3,:2])
#[ [ 5  6]
#  [ 9 10] ]

print(arr[np.ix_([0,2],[1,3])])
#[ [ 2  4]
#  [10 12] ]
```

#### iterator

```python
import numpy as np
arr = np.array([1,2,3,4,5])

it = np.nditer(arr, flag=['c_index'])
while not it.finished :
    idx = it.index
    print(arr[idx], end=' ')
    it.iternext()
# 1 2 3 4 5

arr = np.array([[1,2,3],[4,5,6]])
it = np.diter(arr, flag=['multi_index'])
while not it.finished :
    idx = it.multi_index
    print(arr[idx], end=' ')
    it.iternext()
# 1 2 3 4 5 6
```

#### equal

- 비교연산

```python
import numpy as np

arr1 = np.random.randint(0,10,(2,3))
arr2 = np.random.randint(0,10,(2,3))
print(arr1)
print(np.array_equal(arr1,arr2))
#[ [3 6 5]
#  [3 9 6] ]
# False
```

#### 집계함수

- sum, cumsum, mean, min, max, argmax, std, exp, log10

```python
import numpy as np
arr = np.arange(1,7,1).reshape(2,3).copy()
print(arr)
print(np.sum(arr))
print(np.cumsum(arr))
print(np.mean(arr))
print(np.min(arr))
print(np.argmax(arr))
print(np.std(arr))
print(np.exp(arr))
print(np.log10(arr))
#[ [1 2 3]
#  [4 5 6] ]
# sum : 21
# cumsum : [ 1  3  6 10 15 21]
# mean : 3.5
# min : 1
# argmax : 5
# std : 1.707825127659933
# exp : [ [  2.71828183   7.3890561   20.08553692]
#       [ 54.59815003 148.4131591  403.42879349] ]
# log10 : [ [0.         0.30103    0.47712125]
#         [0.60205999 0.69897    0.77815125] ]
```

#### axis

