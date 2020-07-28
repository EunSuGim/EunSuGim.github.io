---
title: "Python - Closure, Decorator"
excerpt: "Closure, Decorator"
categories: python
tags: python
last_modified_at: 2020-07-15T08:17:00-18:00
---

## First_class  
Closure를 이해할려면 일급함수부터 알아야한다.  
- 객체 지향 프로그래밍에서는 함수도 객체로 포함한다.  
- python은 일급함수를 지원하는 언어로써 함수를 runtime으로 생성할 수 있다.  
- 프로그램의 구성요소(객체)가 다음 조건을 만족하면 first_class_citizen이 된다.  
1. 구성요소가 변수나 데이터 구조의 속성으로 저장될 수 있어야한다.  
```
def my_add(x,y) :
	return x + y

f = my_add
print(f(100,200))
```
1. 함수의 인자로 전달될 수 있어야한다.  
```
def my_add(x,y) :
	return x+y
	
def my_operation(func, arg_list) :
	result = []
	
	for (tmp1,tmp2) in arg_list :
		result.append(func(tmp1,tmmp2))
	
	return result
	
data = [(1,2), (3,4), (5,6)]
print(my_operation(my_add,data))
```
1. 함수의 결과로 리턴될 수 있어야한다.  
```
return my_func
```  

## Closure    
- 일급함수의 개념을 이용하여 scope에 묶인 변수를 바인딩하는 기술이다.(name binding)  
- 어떤 함수를 함수 자신이 가지고 있는 환경과 함께 저장한 레코드  
- scope안의 변수가 소멸되어도 그에 대한 접근을 closure를 통해 할 수 있다.  
- runtime동안에 내가 필요한 함수를 만들어 낼 수 있다.  

ex)    
```
#my_add 함수는 내부함수가 실행되고 리턴되면 종료되는 함수이다.
def my_add(x) :
	def my_add_maker(y) :
		return x + y
		
	return my_add_maker
```  
```
add_5 = my_add(5) # x는 지역변수가되어 5가 저장이된다.
add_10 = my_add(10)

print(add_5(100)) # x는 지역변수이므로 소멸되었지만 closure를 통해 접근할 수 있다.
print(add_10(100)) # 100은 y값이되어 지역변수 x와 연산한다. 
```  
두 함수의 출력결과는 105, 110이 출력된다.


## Decorator  
python에서 기존의 코드에 여러가지 기능을 추가하는 python 구문  
- @사용하여 함수를 decorator선언하여 함수의 전처리와 후처리를 할 수 있다.  
	ex)  
```
import time

def my_outer_func(func):
    def my_inner_func():
        print("함수 수행시작 : {}".format(func.__name__))
        start = time.time()
        func()
        end = time.time()
        print("함수 수행완료 시간 : {}".format(round(end-start,2)))

    return my_inner_func
	
def my_func() :
	result = 1
	for i in range(1,10000) :
		result *= i
	print("함수 호출!!")
decorator_func = my_outer_func(my_func)
decorator_func()
```  
출력 결과는  
```
함수 수행시작 : my_func #전처리
함수 호출!!
함수 수행완료 시간 : 0.06    #후처리
```  

Closure를 사용하여 my_func에 수행하는 함수명과  
수행완료 시간을 알려주는 기능을 추가하였다.  
그런데 my_func같이 해당 기능을 추가해야하는 함수가  
100개이상이라면 어떻게 해야할까?  
그럴때 Decorator가 필요하다.  
```
import time

def my_outer_func(func):
    def my_inner_func():
        print("함수 수행시작 : {}".format(func.__name__))
        start = time.time()
        func()
        end = time.time()
        print("함수 수행완료 시간 : {}".format(round(end-start,2)))

    return my_inner_func

@my_outer_func	
def my_func() :
	result = 1
	for i in range(1,10000) :
		result *= i
	print("함수 호출!!")
	
@my_outer_func
def add_func() :
	result = 1
	for i in range(1,100) :
		result += 1
	print(result)
	
my_func()
add_func()
```  
  
## *args, **kwargs  
또한 decorator는 범위를 정하지않는 인자를 받을 수 있다.  
```
def print_user_name(*args) : #인자의 갯수를 정하지않아도 정상작동한다.
	for name in args :
		print(name)
```   
그리고 딕셔너리 형태로 인자를 받을 수 있다.  
```
def print_user_name(**kwargs) : #인자의 갯수를 정하지않아도 정상작동한다.
	for key, value in kwargs.items() :
		print("{} is {}".format(key, value))

print_user_name(myname="kim")
```
