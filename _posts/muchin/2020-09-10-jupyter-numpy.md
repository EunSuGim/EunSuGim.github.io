---
title: "AI - Numpy"
excerpt: "numpy"
toc: true
toc_sticky: true
categories: ai
tags: ai
last_modified_at: 2020-09-07T08:17:00-18:00
typora-root-url: ..\..\assets\img\muchine
---

## 데이터 분석

#### 기술 분석(Descriptive Analysis)

- 주어진 데이터를 요약/집계하여 결과를 도출하는 것
- 분석 결과를 따로 해석하는 과정이 없다.



#### 탐색적 분석(Exploratory Analysis)

- 여러 변수간 트렌드나 패턴 관계를 찾아내는 분석기법



#### 추론적 데이터 분석(Inferential Analysis)

- 샘플 - 모집단 데이터 분석



#### 예측 분석(Predictive Analysis)

- 머신러닝을 통해서 다양한 통계기법을 동원하여 

  미래 or 발생하지않는 사건에 대해 예측하는 분석기법

  

## Numpy

- Numerical Python
- Vector 와 Matrix 연산에 특화
- pandas, Matplotlib의 기반이 되는 module
- machine, deep learning에서 많이 사용
- ndarray라는 n-차원의 배열을 제공
- jupyter 실행 후 코드 작성



### ndarray

1. python의 list와 유사
2. 같은 데이터타입만 저장가능
3. 파이썬 기반

```python
import numpy as np #jupyter에서는 import를 cell마다 작성해주는것이 좋다.
a = [[1,2,3],[1,2,3],[1,2,3],[1,2,3]]
print(type(a))
# <class 'list'>
print(a) 
# [[1, 2, 3], [1, 2, 3], [1, 2, 3], [1, 2, 3]]
arr = np.array(a, dtype = np.float64)
print(type(arr))
# <class 'numpy.ndarray'>
print(arr)
#[[1. 2. 3.]
# [1. 2. 3.]
# [1. 2. 3.]
# [1. 2. 3.]]

```

#### shape

- 행,열 수정

```python
a = [[1,2,3],[1,2,3],[1,2,3],[1,2,3]]
print(a)
# [[1, 2, 3], [1, 2, 3], [1, 2, 3], [1, 2, 3]]
arr = np.array(a)
arr.shape = (2,6)
print(arr)
# [ [1 2 3 1 2 3]
#   [1 2 3 1 2 3] ]
```

#### astype

- 형 변환

```python
import numpy as np
a = [[1,2,3],[1,2,3],[1,2,3],[1,2,3]]
arr = np.array(a).astype(np.float64)
print(arr)
#[ [1. 2. 3.]
#  [1. 2. 3.]
#  [1. 2. 3.]
#  [1. 2. 3.] ]
```

#### zeros, ones, full, empty

- 초기화없이 공간만 생성 (속도가 빠르다.)

```python
import numpy as np
zero = np.zeros(4)
zero1 = np.zeros((2,2), dtype=np.int64)

print(zero)
# [0. 0. 0. 0.]
print(zero1)
#[ [0 0]
#  [0 0] ]

one = np.ones(4)
print(one)
# [1. 1. 1. 1.]

full = np.full((2,2),4)
print(full)
#[ [4 4]
#  [4 4] ]

empty = np.empty((2,2)) # 기존 메모리에 저장되어있던 값으로 초기화
#[ [1. 1.]
#  [1. 1.] ]
```



#### random

```python
import numpy as np
np.random.seed(10) #랜덤값 유지, 난수의 재현

arr = np.random.randint(0,10,(3,4)) # 0-9까지 난수값의 3행4열의 ndarray생성
print(arr)
#[ [9 4 0 1]
#  [9 0 1 8]
#  [9 0 8 6] ]

arr.resize(2,6)
print(arr)
#[ [9 4 0 1 9 0]
#  [1 8 9 0 8 6] ]
```

