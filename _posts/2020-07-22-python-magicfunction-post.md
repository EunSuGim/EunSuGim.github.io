---
title: "Python - Magic_function"
excerpt: "Magic_function"
categories: python
tags: python
last_modified_at: 2020-07-20T08:17:00-18:00
---
## Magic_function  
미리 정의되어 있는 특별한 메소드들을 재정의 함으로써  인터프리터가 객체 생성, 표현, 연산 등 에 사용할 수 있는 메소드  

## Magic_function 종류
1. __init__  
1. __name__  
1. __add__  
1. __del__  
1. __repr__  
1. __lt__  

## __init__  
객체생성할때 가장 먼저 실행되는 메소드. java의 초기화 생성자 메소드 역할  
``` 
class Students(object) :
    scholarship_rate = 1
    def __init__(self, name, grade):
        self.name = name
        self.grade = grade
		
stu = Students("kim",3)
```  

```
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
    def change_scholarship(cls,rate): 
	#self 대신 cls인자를 추가해줘야한다.
	```  

- static_method	 
   - 추가되는 인자없이 class안에서 정의된 일반 함수  
   
## Information_hiding(정보은닉)
  instance가 가지는 속성은 중요한 데이터이기 때문에 외부에서 직접적으로 access하는건 좋지않다.  
- instace  
   ex) self.__name = name  

- method  
   ex) ```    def __print_date(self): ```  
   
- access할려면 method를 이용해서 사용하도록 처리  
   - def get_name(self):  return self.name  

   - def set_name(self, name) : self.name = name  
