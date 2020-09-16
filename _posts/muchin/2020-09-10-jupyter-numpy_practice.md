---
title: "AI - pandas_practice"
excerpt: "pandas"
toc: true
toc_sticky: true
categories: ai
tags: ai
last_modified_at: 2020-09-16T08:17:00-18:00
typora-root-url: ..\..\assets\img\muchine
---

## 연습문제

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

#### arange

- 특정 규칙에 따라 증가하는 수열 array 생성

```python
import numpy as np
arr = np.arange(3)
# [0 1 2]
arr = np.arange(3,7)
# [3 4 5 6]
arr = np.arange(3,9,2)
arr = np.arange(3,9,step=2)
# [3 5 7]
```

#### linspace

- 두 변수 사이의 값을 간격만큼 띄어 array 생성
- num : 배열 크기, endpoint : 마지막 변수 포함 여부, retstep : 출력 스타일

```python
arr = np.linspace(0, 10, num=5, endpoint=True, retstep=True)
# (array([ 0. ,  2.5,  5. ,  7.5, 10. ]), 2.5)
arr1 = np.linspace(0, 10, num=5, endpoint=True, retstep=False)
# [ 0.   2.5  5.   7.5 10. ]
arr2 = np.linspace(0, 10, num=5, endpoint=False, retstep=False)
# [0. 2. 4. 6. 8.]
```

#### copy

- 독립적인 메모리를 가진 배열 복사

```python
arr = np.array([1,2,3])
arr_copy1 = arr
arr_copy2 = np.copy(arr)
arr_copy[0] = 5
print(arr)
# [5 2 3]
print(arr_copy2)
# [1 2 3]
```

#### Matplotlib

- 차트나 플롯으로 그려주는 데이터 시각화(Data Visualization) 패키지

```python
import numpy as np
from matplotlib import pyplot as plt
plt.plot(["Seoul","Paris","Seattle"], [30,25,55])
plt.xlabel('City')
plt.ylabel('Response')
plt.title('Experiment Result')
plt.show()
```

![image-20200912232442693](/assets/img/muchine/image-20200912232442693.png)

#### mean

- 배열의 평균 구하는 함수

```python
arr = np.array([[5,7],[8,6]])
print(np.mean(arr))
# 6.5
print(np.mean(arr, axis=0))
# [6.5 6.5]
print(np.mean(arr, axis=1))
# [6. 7.]
```

#### std

- 표준편차 구하는 함수

```python
arr = np.array([[4,6],[6,8]])
print(np.std(arr))
# 1.118033988749895
```

#### resize

- 행,열 재배열

```python
arr = np.array([[1,2,3,4,5,6],[7,8,9,10,11,12]])
print(arr)
#[ [ 1  2  3  4  5  6]
#  [ 7  8  9 10 11 12] ]
arr.resize(3,4)
#[ [ 1  2  3  4]
#  [ 5  6  7  8]
#  [ 9 10 11 12] ]
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

np.random.shuffle(arr)
print(arr)
#[ [9 0 8 6]
#  [9 0 1 8]
#  [9 4 0 1] ]

print(np.random.choice(5,4)) #np.random.randint(0,5,4)와 동일
# [0 4 3 0]
print(np.random.choice(5,size=4,replace=False)) #replace = 중복여부
# [1 3 2 4]
point = [0.1, 0, 0.3, 0.6, 0]
print(np.random.choice(5,size=4, p=point)) # 선택확률 설정
# [3 0 3 3]
```

