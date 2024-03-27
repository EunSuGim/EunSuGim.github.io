---
title: "Web - Spring"
excerpt: "Spring"
toc: true
toc_sticky: true
categories: Spring
tags: Spring
last_modified_at: 2020-07-28T08:17:00-18:00
---
## Spring Error 모음
mybatis 연동할려고 테스트했더니 
ERROR: org.springframework.test.context.TestContextManager - Caught exception while allowing TestExecutionListener

Caused by: org.springframework.beans.factory.BeanCreationException




@WebAppConfiguration를 추가해도 안되길래 하루종일 애먹었습니다.
오류내용에 resources 어쩌고해서 resources 전부찾아서 주석하거나 수정한결과

servlet-context.xml에서 resources라인을 주석처리하니 잘돌아갑니다.
더 찾아보니 
pom.xml에서 javax.servlet안에 버전을 업데이트시켜주면된다 난 4.0.1 artifactId도 
servlet-api에서 javax.servlet-api로 변경해야함



## framework란  
library : 특수한 처리를 하기 위해 만들어 놓은 함수집합, jQuery도 라이브러리입니다.  
- 장점 : 내가 모든걸 다 작성할 필요없어 편리합니다.  
- 단점 : 라이브러리의 특징으로써 전체 프로그램의 로직을 담당하지않습니다.  
		

Django는 MVC Model을 기반으로 이용합니다.  
- MVC : Model, View, Controller => Model은 DB, View는 화면처리, Controller는 로직  
- MVT : Model, View, Template => Model은 DB처리, View는 로직, Template는 화면처리  
	
## Django 설치  
