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
import numpy as np
import pandas as pd
df = pd.read_csv('./data/mpg.txt')

# display(df.head())

boolean_mask = (df['manufacturer'] == 'chevrolet') | (df['manufacturer'] == 'ford') | (df['manufacturer'] == 'honda')

result = df.loc[boolean_mask]

result_mean = result['hwy'].mean()

display(result_mean)
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

#### 5번

```python
# 5. mpg 데이터는 연비를 나타내는 변수가 2개입니다. 
# 두 변수를 각각 활용하는 대신 하나의 통합 연비 변수를 만들어 사용하려 합니다. 
# 평균 연비 변수는 두 연비(고속도로와 도시)의 평균을 이용합니다. 
# 회사별로 "suv" 자동차의 평균 연비를 구한후 내림차순으로 정렬한 후 1~5위까지 데이터를 출력하세요.
import numpy as np
import pandas as pd

df = pd.read_csv('./data/mpg.txt')

display(df)

df['avg'] = (df['cty'] + df['hwy']) / 2 

display(df[df['class']=='suv'])
```

![image-20200920000010075](/assets/img/muchine/image-20200920000010075.png)

#### 6번

```python
# 6. mpg 데이터의 class는 "suv", "compact" 등 자동차의 특징에 따라 
# 일곱 종류로 분류한 변수입니다. 어떤 차종의 도시 연비가 높은지 비교하려 합니다. 
# class별 cty 평균을 구하고 cty 평균이 높은 순으로 정렬해 출력하세요.
import numpy as np
import pandas as pd

df = pd.read_csv('./data/mpg.txt')

display(df)

display(df['cty'].groupby(df['class']).mean().sort_values(ascending=False))

```

![image-20200927222042104](/assets/img/muchine/image-20200927222042104.png)

#### 7번

```python
# 7. 어떤 회사 자동차의 hwy(고속도로 연비)가 가장 높은지 알아보려 합니다. 
# hwy(고속도로 연비) 평균이 가장 높은 회사 세 곳을 출력하세요.
import numpy as np
import pandas as pd

df = pd.read_csv('./data/mpg.txt')

display(df)

display(df['hwy'].groupby(df['manufacturer']).mean().sort_values(ascending=False)[:3])
```

![image-20200927222130614](/assets/img/muchine/image-20200927222130614.png)

#### 8번

```python
# 8. 어떤 회사에서 "compact" 차종을 가장 많이 생산하는지 알아보려고 합니다. 
# 각 회사별 "compact" 차종 수를 내림차순으로 정렬해 출력하세요.
import numpy as np
import pandas as pd

df = pd.read_csv('./data/mpg.txt')

boolean_mask = df['class'] == 'compact'

compact_df = df.loc[boolean_mask]


display(compact_df['class'].groupby(df['manufacturer']).count().sort_values(ascending=False))
```

![image-20200927222200729](/assets/img/muchine/image-20200927222200729.png)