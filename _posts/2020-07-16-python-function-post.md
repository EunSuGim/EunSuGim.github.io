---
title: "Python - Function"
excerpt: "Function"
categories: python
tags: python
last_modified_at: 2020-07-16T08:17:00-18:00
---
## Function
함수 : 특정작업을 수행하는 일정량의 코드 모음  
- ex) def my_sum()  

가변 함수 : def my_sum(*args)  

## Default parameter
- def my_operator(a,b,c=True) : 마지막 인자만 설정가능  
- python함수의 인자는 mutable, immutable 둘 중 하나  
- call-by-value & call-by-reference X와 유사  

## 실인자 데이터가 변하는 경우와 변하지 않는 경우
```python
def my_func(tmp_number, tmp_list) :
	tmp_number = tmp_number + 100
	tmp_list.append(100)
	
data_x = 10 #immutable
data_list = [10] #mutable

my_func(data_x,data_list)
```

## 함수 id()
객체의 고유 주소값을 return하는 함수
파이썬은 숫자인 경우 대략 0~256까지는 많이 사용하는 객체(값) 이여서 하나의 객체를 가르킨다.  
```python
my_list1 = [1,2,3]
my_list2 = [1,2,3]

print(id(my_list1)) # 주소값 2685740667400
print(id(my_list2)) # 주소값 2685740667912 -> 주소값이 다르다

x = 100 #둘다 주소값이 같다.
y = 100
```

## Lambda expression
익명함수(anonymous function)  
변수에 저장, 함수의 인자로 사용  
함수의 리턴값으로 함수를 return

```python
my_lambda = lambda x1, x2
my_lambda(10,20)
```

lambda는 함수가 아니다 lambda는 대체식이다.
```python
my_lambda(10,20) # 10+20으로 코드자체를 변환
```
