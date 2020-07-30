---
title: "Python - Magic_function"
excerpt: "Magic_function"
toc: true
toc_sticky: true
categories: python
tags: python
last_modified_at: 2020-07-20T08:17:00-18:00
---
## Magic_function  
미리 정의되어 있는 특별한 메소드들을 재정의 함으로써  인터프리터가 객체 생성, 표현, 연산 등 에 사용할 수 있는 메소드  

미리 정의되어 있는 특별한 메소드들을 재정의 함으로써  
인터프리터가
객체 생성, 표현, 연산 등 에 사용할 수 있는 메소드  

## Magic_function 종류
1. __init__  
1. __name__  
1. __add__  
1. __del__  
1. __repr__  
1. __lt__  

## __init__  
객체가 생성될때 가장 먼저 실행되는 초기화메소드.  
생성자(Constructor), Initializer라고 불림  
``` 
class Students(object) :
    scholarship_rate = 1
    def __init__(self, name, grade):
        self.name = name
        self.grade = grade
		print("Constructor")
stu = Students("kim",3)
```  
## __del__  
객체가 소멸될때 실행되는 메소드. 소멸자(Destructor).  
명시적으로 객체를 메모리에서 지울 수 있다.
```
class Students(object) :
	def __del__(self) :
		print("Destructor")
		
stu = Students()

del stu
```  
결과는 Destructor가 출력된다.  
## __add__  
클래스의 객체에 대해서 연산자를 사용할 수 있다.  
```
class Students(object) :
    def __init__(self, grade):
        self.grade = grade
		print("Constructor")
	def __add__(self,other) :
		return self.grade * other.grade
		
stu1 = Students(3)
stu2 = Students(6)

print(stu1 + stu2)
```
결과는 18이 나온다.  

## __repr__
객체를 출력할때 사용하는 메소드.  
자바의 toString과 비슷
```
class Students(object) :
    def __init__(self, grade):
        self.grade = grade
		print("Constructor")
	def __repr__(self) :
		return "학생 점수는 {} ".format(self.grade)
		
stu = Students(3)
print(stu)
```  
결과는 "학생 점수는 3 "이 출력된다.  

## __lt__  
객체간 비교할때 앞에 인자를 기준으로 비교, 부등식 기호사용  
```
class Students(object) :
    def __init__(self, grade):
        self.grade = grade
		print("Constructor")
	def __lt__(self,other) :
		if self.grade > other.grade :
			return True
		else :
			return False
stu1 = Students(11)
stu2 = Students(8)

print(stu1 > stu2)
```  
결과는 True가 출력된다.