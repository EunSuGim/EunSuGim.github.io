---
title: "Python - Data_Type"
excerpt: "Data_Type"
categories: python
tags: python
last_modified_at: 2020-07-15T08:17:00-18:00
---
## Data_Type 
 
Built-in data_type  
type()을 사용하여 자료형을 확인 할 수 있다.

## Data_Type 종류  

1. Numeri  
1. Text_Sequence  
1. Set  
1. Mapping  
1. Bool
1. date,date_time

### Numeric  
int, float, complex(복소수) 등

### Text_Sequence(str)  
- *indexing*  
   ex) my_var = "hello" => print(my_var[-1]) = "o"  
- *slicing*  
   ex) my_var[0:3] = "my_", my_var[:]  
- *in, not_in*  
   ex) print("hello" in my_var) = True, print("hello" not in my_var)  
- *formatting*  
   ex) myStr = "i have {}apples and {}bananas".format(10,30)  
   upper(), lower(), strip()  
	- strip : 공백 없애기 strip() ex) "  test is test".strip => "test is test"  
- *tuple*  
   생성되면 변경 X list와 형변환가능 ex) a = 1,3 => b = list(a)  

## Mapping  
*ex) a = {"name" : "kim", "age" : 49}*  
	- *key, value 값으로 나뉘어짐.※keys(), values()는 list처럼 보이지만 list형이 아니다.*  
	   ex) key_list = a.keys(), value_list = a.values() 
- *key값 중복불가*  
   ex) a = {"name" : "kim", "age" : 19, "name" : "lee"} print=> {'name' : 'lee',  'age' : 19}  

## Bool
"", [], {}, (), 0, None => false로 간주

## Set
집합 자료형  
순서, 중복 X

## date,date_time
date는 날짜, datetime은 시간  
   ex) my_str = "today is {}year, {}month, {}day.", today = date.today(), today =datetime.today()  
- *date*  
   ex) my_str.format(today.year, today.month, today.day)
- *datetime*  
   ex) my_str.format(today.hour, today.minute, today.second)
- *days*  
   날짜 계산 하지만 month와 year은 지원을 안한다.  
   ex) days = timedelta(days=-3)  
	- month와 year도 계산할려면 dateutil 모듈이 필요하다.  
		ex) from dateutil.relativedelta import relativedelta  
	- months는 현재 달에서 더하거나 빼는 것, month는 특정 달로 바꾸는 것.  
- *parse*  
   문자열은 parse를 사용하여 date타입으로 변환한다.
   ex)from dateutil.parser import parse, my_date = parse("2020-07-15")