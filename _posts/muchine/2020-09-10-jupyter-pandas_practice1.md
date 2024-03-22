---
title: "AI - pandas_practice(1)"
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

  1. 사용자가 평가한 모든 영화의 전체 평균 평점
  2. 각 사용자별 평균 평점
  3. 각 영화별 평균 평점
  4. 평균 평점이 가장 높은 영화의 제목(동률이 있을 경우 모두 출력)
  5. Comedy영화 중 가장 평점이 낮은 영화의 제목
  6. 2015년도에 평가된 모든 Romance 영화의 평균 평점은?

 

## Code

#### 1번

```python
# 1. 사용자가 평가한 모든 영화의 전체 평균 평점
import numpy as np
import pandas as pd

df_rating = pd.read_csv('./data/ratings.csv')

display(df_rating['rating'].mean())
# 3.501556983616962
```

#### 2번

```python
# 2. 각 사용자별 평균 평점
import numpy as np
import pandas as pd

df_rating = pd.read_csv('./data/ratings.csv')

display(df_rating['rating'].groupby(df_rating['userId']).mean())
```

![image-20200928012652331](/image-20200928012652331.png)

#### 3번

```python
# 3. 각 영화별 평균 평점
import numpy as np
import pandas as pd

df_rating = pd.read_csv('./data/ratings.csv')
df_movie = pd.read_csv('./data/movies.csv')

merge_df = pd.merge(df_rating,df_movie, on='movieId', how = 'inner')

display(merge_df['rating'].groupby([merge_df['movieId'], merge_df['title']]).mean())
```

![image-20200928012723657](/image-20200928012723657.png)

#### 4번

```python
# 4. 평균 평점이 가장 높은 영화의 제목(동률이 있을 경우 모두 출력)
import numpy as np
import pandas as pd

df_rating = pd.read_csv('./data/ratings.csv')
df_movie = pd.read_csv('./data/movies.csv')

merge_df = pd.merge(df_rating, df_movie, on='movieId', how = 'inner')
high = merge_df['rating'].groupby([merge_df['movieId'], merge_df['title']]).mean()

high_rating = high[high==high.max()]

display(high_rating)
```

![image-20200928012740131](/image-20200928012740131.png)

#### 5번

```python
# 5. Comedy영화 중 가장 평점이 낮은 영화의 제목
import numpy as np
import pandas as pd

df_rating = pd.read_csv('./data/ratings.csv')
df_movie = pd.read_csv('./data/movies.csv')

merge_df = pd.merge(df_rating, df_movie, on ='movieId', how='inner')

comedy_df = merge_df.loc[merge_df['genres'].str.contains('Comedy')]

low = comedy_df['rating'].groupby([comedy_df['movieId'], comedy_df['title']]).mean()

low_rating = low[low==low.min()]

display(low_rating)
```

![image-20200928012754773](/image-20200928012754773.png)

#### 6번

```python
# 6. 2015년도에 평가된 모든 Romance 영화의 평균 평점은?
import numpy as np
import pandas as pd
import time
from datetime import datetime

start_date = time.mktime(datetime.strptime('2015-01-01 0:0:1', '%Y-%m-%d %H:%M:%S').timetuple())
end_date = time.mktime(datetime.strptime('2015-12-31 23:59:59', '%Y-%m-%d %H:%M:%S').timetuple())


merge_df = pd.merge(df_rating, df_movie, on ='movieId', how='inner')

romance_df = merge_df.loc[merge_df['genres'].str.contains("Romance")]

boolean_mask = (romance_df['timestamp'] > start_date) & (romance_df['timestamp'] < end_date)

result_df = romance_df[boolean_mask]['rating'].mean()

display(result_df)
# 3.396375098502758
```


