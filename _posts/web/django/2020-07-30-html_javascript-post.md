---
title: "Web - HTML,JavaScript"
excerpt: "HTML,JavaScript"
toc: true
toc_sticky: true
categories: web
tags: web
last_modified_at: 2020-07-28T08:17:00-18:00
---
## HTML  
HTML은 tag로 구성된 언어입니다.  
tag에는 여러 특성이 있습니다.  
- _시작태그와 닫는 태그로 구성된 태그_  
	ex) `<title>Title</title>`  

- _시작태그만 가지고 있는 태그_  
	ex) `<meta charset="UTF-8">`  

- _block level element_  
	무조건 1라인을 차지  
- _inline element_  
	내용에 대한 영역만 차지  

tag는 중첩구조를 가질 수 있습니다.  
하나의 tag가 다른 tag들을 포함할 수 있습니다.  
이때 부모자식, 후손관계가 성립됩니다.  
tag와 tag안에 포함된 요소들을 포함해서 element라고 부릅니다.  

## HTML 구성  
HTML은 크게 2가지 부분으로 구성됩니다.  
_\<head\>_ : 설정부분  
_\<body\>_ : web browser에서 rendering 할 데이터.  
class : 여러 스타일들을 그룹으로 묶어 한번에 지정할 수 있게 사용됩니다.  
\<img\> : 이미지삽입을 위한 tag, src="이미지경로"  

```html
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Title</title>
        <style>
            .myclass {
                color: red;
                background-color: yellow;
                font-size: 30pt;
            }

        </style>
    </head>
    <body>
        <h1 class="myclass">아우성!!</h1>
        <h2>아우성!!</h2>
        <h3 class="myclass">아우성!!</h3>
        <span>이것은 소리없는 아우성!!</span>
        <img src="image/car.jpg" width="300"
             data-author="홍길동">
        <!-- ul => unordered list -->
        <ul>
            <li>서울</li>
            <li class="myclass">인천</li>
            <li>제주</li>
        </ul>
        <ol>
            <li>홍길동</li>
            <li>김길동</li>
            <li>신사임당</li>
        </ol>
        <a href="http://www.naver.com">여기를 클릭클릭!!</a>
        <!-- 사용자 입력 양식 -->
        <input type="button" value="버튼을 누르세요!!">
        <input type="text">
        <input type="date">
        <input type="color">
    </body>
</html>
```  

## JavaScript  
web client에서 실행되는 언어입니다.  
요즘에는 서버용 개발언어로 사용하기도합니다.(node-js)  
HTMl안에 직접적으로 사용도하지만 보통 .js파일로 분리하여  
관리합니다.  

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
	<!-- javascript를 작성해놓은 js파일을 불러옵니다.-->
    <script src="js/my_script.js"></script> 
</head>
<body>
    <div>소리없는 아우성!!</div>
</body>
</html>
```

가독성을 위해 javascript만 따로 분리해서 관리합니다.  
java와 문법이 굉장히 유사하고 함수를 사용할 수 있습니다.  

```javascript
//my_script.js파일이예요.
//변수선언
//다른 언어처럼 따로 자료형에따라 선언할 필요가 없습니다.
var tmp = 3.14 
var tmp2 = "Hello"
var tmp3 = True
var tmp4 = [1,2,3,4]

//객체 표현방법
var tmp5 = {name : "kim", age : 25}
console.log(tmp5.name)
```

var는 재선언을 해도 아무런 오류가 발생하지않아  
문제가 생길 수 도 있어 let,const가 만들어졌습니다.  
- let : 변수 재선언이 불가능하지만 재할당이 가능합니다.  
	
```javascript
let test = 3
let test = 5 //에러가 발생합니다.
test = 8 //정상 작동합니다.
```

- const : 변수 재선언과 재할당이 되지않습니다.  

```javascript
const test = 6
const test = 8 //에러가 발생합니다.
test = 10 //에러가 발생합니다.
```

javascript는 함수를 사용할 수 있습니다. 함수에는 선언적 함수와 익명함수로 나뉘어집니다.  
- 선언적 함수 : 선언적 함수는 함수 이름이 있습니다.  

```javascript
function my_func(x,y) {
	return x+y
}
```  

- 익명 함수 : 일명 lambda(람다)함수로써 이름이 없고 변수에  
		바로 저장하여 사용합니다.  
		lambda함수는 정말 많이 사용되므로 함수사용할때마다 설명하겠습니다.  

```javascript
var test = function(x,y){
	return x+y
}
```
