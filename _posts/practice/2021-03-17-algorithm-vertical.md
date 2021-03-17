---
title: "Algorithm - Vertical"
excerpt: "Algorithm"
toc: true
toc_sticky: true
categories: algorithm
tags: Practice
last_modified_at: 2021-03-17T08:17:00-18:00
typora-root-url: ..\..\assets\img\Algorithm
---

## Question
문자열을 세로로 출력시키시오.



## Input / Output

| phone_book  | return                                             |
| ----------- | -------------------------------------------------- |
| "test"      | t<br />e<br />s<br />t                             |
| "good boy." | g<br />o<br />o<br />d<br /> <br />b<br />o<br />y |



## Answer



```java
class Solution {
    public String solution(String sent) {
      	String answer = "";
      	String[] test = sent.split("");
    	
      	for(String t : test) {
      		System.out.println(t);
      	}
        return answer;
    }
}
```



### PS

java에는 split이있어서 구현이 쉬웠습니다.