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

### 기술 분석(Descriptive Analysis)

- 주어진 데이터를 요약/집계하여 결과를 도출하는 것
- 분석 결과를 따로 해석하는 과정이 없다.



### 탐색적 분석(Exploratory Analysis)

- 여러 변수간 트렌드나 패턴 관계를 찾아내는 분석기법



### 추론적 데이터 분석(Inferential Analysis)

- 샘플 - 모집단 데이터 분석



### 예측 분석(Predictive Analysis)

- 머신러닝을 통해서 다양한 통계기법을 동원하여 

  미래 or 발생하지않는 사건에 대해 예측하는 분석기법

  

## Numpy

- Numerical Python
- Vector 와 Matrix 연산에 특화
- pandas, Matplotlib의 기반이 되는 module
- machine, deep learning에서 많이 사용
- ndarray라는 n-차원의 배열을 제공
- jupyter 실행 후 코드 작성



#### ndarray

1. python의 list와 유사
2. 같은 데이터타입만 저장가능

```python
import numpy as np
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

- shape

  ```
  
  ```

  



