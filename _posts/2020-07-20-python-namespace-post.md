---
title: "Python - Namespace"
excerpt: "Namespace"
categories: python
tags: python
last_modified_at: 2020-07-16T08:17:00-18:00
---
## Namespace
객체가 가지는 데이터를 나누어서 관리하는 공간  

instance_namespace ⊂ class_namespace ⊂ superclass_namespace

## 동적으로 속성이나 method를 추가 할 수 있다.
``` 
class Students(object) :
    scholarship_rate = 1
    def __init__(self, name, grade):
        self.name = name
        self.grade = grade
		
stu = Students("kim",3)
```
instance에 없는 변수를 선언해도 오류가 안난다.  
   ex) ``` stu.dept = "컴퓨터" ```
class명으로 선언하지않으면 class_namespace에서 가져오지않고 새로운 instace를 생성한다.  
   ex) ```
stu.scholarship_rate = 4

print(stu.scholarship_rate)  #4가 출력된다.

print((Students.scholarship_rate)) # 1이 출력된다.
```
- instace_method  
   - 하나의 instace에 한정된 데이터를 생성, 변경, 참조하기 위해 사용 

- class_method  
   - class안에서 정의된 일반 함수이고 클래스를 인자로 받아서 사용  
     ex) ```
    @classmethod
    def change_scholarship(cls,rate): #self 대신 cls인자를 추가해줘야한다.```

- static_method	 
   - 추가되는 인자없이 class안에서 정의된 일반 함수
## Information_hiding(정보은닉)
  instance가 가지는 속성은 중요한 데이터이기 때문에 외부에서 직접적으로 access하는건 좋지않다.  
- instace
   ex) self.__name = name  

- method  
   ex) ```    def __print_date(self): ```  
   
- access할려면 method를 이용해서 사용하도록 처리
   ex)
   ```
    def get_name(self):
        return self.name

    def set_name(self, name) :
        self.name = name
		```
	
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
