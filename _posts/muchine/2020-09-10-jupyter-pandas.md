```
title: "AI - pandas"
excerpt: "pandas"
toc: true
toc_sticky: true
categories: ai
tags: ai
last_modified_at: 2020-09-07T08:17:00-18:00
typora-root-url: ..\..\assets\img\muchine
```









# Pandas 



ndarray(NumPy)를 기본 자료구조로 이용

pandas는 두개의 또 다른 자료구조 이용



#### Series

Series: 동일한 데이터 타입의 복수개의 성분으로 구정되는 자료구조(1차원)



#### DataFrame

DataFrame : 엑셀에서 Table과 같은 개념. Database의 Table과 같은 개념. Series로 구성

conda install pandas

Database

mysql설치

bin 폴더 > mysqld

close : 새  cmd창 실행 mysqladmin -u root shutdown

% 그냥 종료시 db파일이 깨질 수 있기때문

mysql -u root(서버실행상태에서)

create user data identified by "data";

create user data@localhost identified by "data";

create database library;

grant all privileges on library.* to data;

grant all privileges on library.*to data@localhost;

exit;

mysql -u data -p library <_BookTableDump.sql

anaconda: 

pip install pymysql

import pymysql.cursors