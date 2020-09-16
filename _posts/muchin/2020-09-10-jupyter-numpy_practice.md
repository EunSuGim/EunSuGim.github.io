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

#### 문제

 1. displ(배기량)이 4 이하인 자동차와 5 이상인 자동차 중 
 어떤 자동차의 hwy(고속도로 연비)가 평균적으로 더 높은지 확인하세요.

 2. 자동차 제조 회사에 따라 도시 연비가 다른지 알아보려고 한다. 
 "audi"와 "toyota" 중 어느 manufacturer(제조회사)의 cty(도시 연비)가 
 평균적으로 더 높은지 확인하세요.

 3. "chevrolet", "ford", "honda" 자동차의 고속도로 연비 평균을 알아보려고 한다. 
 이 회사들의 데이터를 추출한 후 hwy(고속도로 연비) 평균을 구하세요.

 4. "audi"에서 생산한 자동차 중에 어떤 자동차 모델의 hwy(고속도로 연비)가 
 높은지 알아보려고 한다. "audi"에서 생산한 자동차 중 hwy가 1~5위에 해당하는 
 자동차의 데이터를 출력하세요.

 5. mpg 데이터는 연비를 나타내는 변수가 2개입니다. 
 두 변수를 각각 활용하는 대신 하나의 통합 연비 변수를 만들어 사용하려 합니다. 
 평균 연비 변수는 두 연비(고속도로와 도시)의 평균을 이용합니다. 
 회사별로 "suv" 자동차의 평균 연비를 구한후 내림차순으로 정렬한 후 1~5위까지 데이터를 출력하세요.

 6. mpg 데이터의 class는 "suv", "compact" 등 자동차의 특징에 따라 
 일곱 종류로 분류한 변수입니다. 어떤 차종의 도시 연비가 높은지 비교하려 합니다. 
 class별 cty 평균을 구하고 cty 평균이 높은 순으로 정렬해 출력하세요.

 7. 어떤 회사 자동차의 hwy(고속도로 연비)가 가장 높은지 알아보려 합니다. 
 hwy(고속도로 연비) 평균이 가장 높은 회사 세 곳을 출력하세요.

 8. 어떤 회사에서 "compact" 차종을 가장 많이 생산하는지 알아보려고 합니다. 
 각 회사별 "compact" 차종 수를 내림차순으로 정렬해 출력하세요.
 
 

## Code

#### 1번

```python
# 1. displ이 4이하인 자동차와 5이상인 자동차 중 어떤 자동차의 hwy가 평균적으로 높은지 확인

import numpy as np
import pandas as pd

df = pd.read_csv('./data/mpg.txt')

display(df.head())

displ_4_df = df.loc[df['displ'] <= 4]
displ_5_df = df.loc[df['displ'] >= 5]

under_4 = displ_4_df['hwy'].mean()
high_5 = displ_5_df['hwy'].mean()

print('under_4 : {}'.format(under_4))
print('high_5 : {}'.format(high_5))

# under_4 : 25.96319018404908
# high_5 : 18.07894736842105
```

#### 2번

```python
# 2. 'audi' 와 'toyota' 중 어느 제조회사의 cty가 평균적으로 더 높은지 확인

df = pd.read_csv('./data/mpg.txt')

display(df.head())

manu_audi = df.loc[df['manufacturer'] == 'audi']
manu_toyota = df.loc[df['manufacturer'] == 'toyota']

audi_cty = manu_audi['cty'].mean()
toyota_cty = manu_toyota['cty'].mean()

print('audi : {}'.format(audi_cty))
print('toyota : {}'.format(toyota_cty))

# audi : 17.61111111111111
# toyota : 18.529411764705884
```

#### 3번

```python
# 3. "chevrolet", "ford", "honda" 자동차의 고속도로 연비 평균을 알아보려고 한다. 
# 이 회사들의 데이터를 추출한 후 hwy(고속도로 연비) 평균을 구하세요.

df = pd.read_csv('./data/mpg.txt')

display(df.head())

manu_chev = df.loc[df['manufacturer'] == 'chevrolet']
manu_ford = df.loc[df['manufacturer'] == 'ford']
manu_honda = df.loc[df['manufacturer'] == 'honda']

chev_hwy = manu_chev['hwy'].mean()
ford_hwy = manu_ford['hwy'].mean()
honda_hwy = manu_honda['hwy'].mean()

result = (chev_hwy + ford_hwy + honda_hwy) / 3
print("avg : {}".format(result))

# avg : 24.603430799220273
```

#### 4번

```python
# 4. "audi"에서 생산한 자동차 중에 어떤 자동차 모델의 hwy(고속도로 연비)가 
# 높은지 알아보려고 한다. "audi"에서 생산한 자동차 중 hwy가 1~5위에 해당하는 
# 자동차의 데이터를 출력하세요.

manu_audi = df.loc[df['manufacturer'] == 'audi']

display(manu_audi.sort_values(by=['hwy'], ascending=False).head())
```

![image-20200916222005547](/assets/img/muchine/image-20200916222005547.png)

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

