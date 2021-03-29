---
title: "Web - jQeury"
excerpt: "jQeury"
toc: true
toc_sticky: true
categories: web
tags: web
last_modified_at: 2020-07-28T08:17:00-18:00
---
## jQeury
javascript의 오븐소스 라이브러리입니다.  
jQeury를 사용하여 스크립트를 더욱 효율적이고 빠르게 개발가능합니다.  

```HTML
<!-- jquery사용하기위한 HTML파일입니다. -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <!-- jQuery를 CDN방식으로 이용 -->
    <script
            src="https://code.jquery.com/jquery-2.2.4.min.js"
            integrity="sha256-BbhdlvQf/xTY9gja0Dq3HiwQF8LaCRTXxZKRutelT44="
            crossorigin="anonymous"></script>
    <script src="js/jQuery.js"></script>
</head>
<body>
    <h1>jQuery 연습입니다.!!</h1>
    <div>
        <ul>
            <li class="region">서울</li>
            <li id="haha">인천</li>
            <li class="region">강원</li>
        </ul>
        <ol>
            <li id="hong">홍길동</li>
            <li>신사임당</li>
            <li>강감찬</li>
        </ol>
    </div>
    <input type="button" value="클릭클릭!!"
           onclick="my_func()">
</body>
</html>
```

## 사용방법  
jQuuery.js파일을 만든 후 function하나를 만듭니다.  
가장 먼저 공부해야할 것은 선택자(selector)입니다.  
1. 전체 선택자(univeral selector)  
	ex) `$('*').css("color","red")`  
1. 태그 선택자(tag selector)  
	ex) `$("li").remove()`  
1. 아이디 선택자(id selector)  
	- 인자가 없으면 값을 알아오라는 의미  
		`$("#haha").text()`  
	- 인자가 있으면 값을 변경하라는 의미  
		`$("#haha").text("kim")`  
1. 클래스 선택자(class selector)  
	ex) `$(.region").css("background-color","red")`  
1. 구조 선택자  
	- 자식,후손 선택자  
		
		```
		$("ol > li").css("color","red")
		$("div li").css("color","pink")
		```
	
	- 형제 선택자  
		
		```
		$("#haha + li").remove()
		$("#haha ~ li").remove()
		```
		
1. 속성 선택자  
	```
	$("[id]").css("color","pink")
	$("[id=haha]").css("color","red")
	```



