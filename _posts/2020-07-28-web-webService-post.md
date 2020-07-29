---
title: "Web - WebService"
excerpt: "web_service"
toc: true
toc_sticky: true
categories: web
tags: web
last_modified_at: 2020-07-28T08:17:00-18:00
---
## Internet?
일반적으로 하나의 컴퓨터를 standalone으로 사용하지 않고  
여러개의 컴퓨터를 network로 묶어서 사용합니다.
- Local Area Network  
- Network로 구성된 전세계의 Network (internet)  
- 인터넷이란 용어는 물리적인 네트워크 망을 지칭하는 용어  


## Service
인터넷을 잘 이용하기 위해서 인터넷안에서 여러가지 프로그램이  
동작하고 있어야하는데 그런  프로그램을 Service라고 부릅니다.  
- email  
- torrent  
- web_service : HTML,CSS,JavaScript를 이용해서 Web page를 만들고,  
		web_server가 이 web page를 web_client에게 전송해서 데이터를 주고받는 서비스.  

## WebService의 기본구조  
1. CS구조를 기본으로합니다
	- CS구조 : Client -Server 구조를 의미
1. ex) Web_client(Web Browser - chrome,IE,Safari...)  
	Web_server(본인이 만들거나 일반적인 상용프로그램 사용)  
  
1. 정적과 동적  
	정적 웹 서비스(static web service)  
		- HTML, CSS, JavaScript  
	동적 웹 서비스(dynamic web service)  
		- HTML, CSS, JavaScript + Python  
		
## 개발환경  
개발툴은 WebStorm을 이용합니다.  
PyCharm을 만든회사로 HTML,CSS,JavaScript를 기본을 쌓기위해  
사용하기 좋은 툴 중 하나입니다.  
프로그램을 설치 후 프로젝트를 하나 생성해서 html파일을 하나 생성해봅시다.  

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <!-- 일반적인 설정이 와요!!  -->
        <meta charset="UTF-8">
        <title>Title</title>
        <style>
           h1 {
              color : red;
           }
        </style>
        <script>
            function my_func(){
                alert("소리없는 아우성!!");  // 경고창을 출력!
            }
        </script>
    </head>
    <body>
        <!-- BROWSER에 출력하고 싶은 내용이 와요!!  -->
        <h1>이것은 소리없는 아우성!! 껄껄껄!!</h1>   <!-- heading 1-->`
        <input type="button" value="클릭클릭!!" onclick="my_func()">`
        <br>
        <img src="image/car.jpg">
        <!-- element, tag, property(attribute) -->
    </body>
</html>
```  

Web 서버가 web 클라이언트에게 저공할 HTMl을 만들었음.
