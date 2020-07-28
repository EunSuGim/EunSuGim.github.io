---
title: "Python - Module,Exception"
excerpt: "Module,Exception"
categories: python
tags: python
last_modified_at: 2020-07-28T08:17:00-18:00
---
## Module
module은 함수나 변수 또는 클래스를 모아놓은 파일을 지칭  
다른 python파일에서 불러와 사용할 수 있어 코드의 재사용성과 관리(객체로 관리)가 용이하다.  
python의 모듈은 크게 2가지로 구분된다.  
- C언어로 구성된 binary module  
- python언어로 구현된 일반 module  




## 사용방법

``` 
import sys
print(sys.path)
sys.path.append("c:/python_data") #module을 저장할 폴더 지정
```  

모듈 선언 방법  

```
import module1	#모듈명 그대로 사용
print(module1.my_pi)

import module1 as m1 #모듈명을 지정하여 사용
print(m1.my_pi)

from module1 import my_pi #모듈의 특정기능을 사용, 다른 기능은 사용하지못함.
print(my_pi)
```  
   
## exception(예외)  
error에는 compile time error(문법오류)와  
runtime error(실행시 발생오류)가 있는데  
특정 runtime error들은 비저상 종료되지않고 프로그램을  
지속적으로 수행시킬 수 있다.  

```
def my_func(my_list) :
	total = 0
	
	try:
		total = my_list[0] + my_list[1]
		print("try가 실행")
	except Exception :
		print("except가 실행")
	finally:
		print("무조건 수행")
```

- try  
	try안에서 프로그램은 오류가 발견되기전까지 실행된다.  
- except  
	try구문에서 오류가 발생했을 경우 실행된다.  
	여러 except명이 있다.ex)ValueError,OSError  
- finally  
	try,except 구별없이 마지막에 항상 실행되는 구문이다.
	

  instance가 가지는 속성은 중요한 데이터이기 때문에 외부에서 직접적으로 access하는건 좋지않다.  
- instace  
   ex) self.__name = name  

- method  
   ex) ```    def __print_date(self): ```  
   
- access할려면 method를 이용해서 사용하도록 처리  
   - def get_name(self):  return self.name  

   - def set_name(self, name) : self.name = name  
