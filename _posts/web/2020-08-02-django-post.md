---
title: "Web - Django"
excerpt: "Django"
toc: true
toc_sticky: true
categories: web
tags: web
last_modified_at: 2020-07-28T08:17:00-18:00
---
## Django  
python으로 만들어진 오픈소스, web_application을 쉽게 작성할 수 있도록 도와주는 framework  

## framework란  
library : 특수한 처리를 하기 위해 만들어 놓은 함수집합, jQuery도 라이브러리입니다.  
- 장점 : 내가 모든걸 다 작성할 필요없어 편리합니다.  
- 단점 : 라이브러리의 특징으로써 전체 프로그램의 로직을 담당하지않습니다.  
		
Django는 MVC Model을 기반으로 이용합니다.  
- MVC : Model, View, Controller => Model은 DB, View는 화면처리, Controller는 로직  
- MVT : Model, View, Template => Model은 DB처리, View는 로직, Template는 화면처리  
	
## Django 설치  
pip를 이용해서 Django를 설치합니다.  
- pip : python install package
- PyPI : (python Package Index)라는 reposistory에 있는 Django를 설치합니다.  

CMD창에 `pip install Django` 를 입력합니다.  

- ![Django 설치](/assets/img/capture1.PNG)  

설치가 완료되었으면, C드라이브에 'python-Django'라는 폴더를 생성해줍니다.  
해당 폴더안에서 `django-admin startproject mysite`를 입력합니다.  

- ![](/assets/img/capture2.PNG)  

그 후 mysite폴더명을 'MyPoll'로 변경해주세요.  
- ex) c:/python-Django/MyFirstWebPoll/mysite  
	내부의 프로젝트와 헷갈릴 수가 있기때문에 변경해줍니다.  

이제 프로젝트안에 하나의 application을 추가합니다.  
'MyPoll'안에서 `python manage.py startapp polls`를 입력해줍니다.  
파이참을 실행합니다.


