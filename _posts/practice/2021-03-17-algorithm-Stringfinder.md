---
title: "Algorithm - StringFinder"
excerpt: "Algorithm"
toc: true
toc_sticky: true
categories: algorithm
tags: Practice
last_modified_at: 2021-03-17T08:17:00-18:00
typora-root-url: ..\..\assets\img\Algorithm
---

## Question
문자열에서 첫 번째 일치하는 곳부터 문자열을 출력시키며, 만약 일치되는 것을
발견하지 못하면, "not found"라고 출력시킨다.



## Input / Output

| String                                          | return            |
| ----------------------------------------------- | ----------------- |
| ["Return a pointer to the first character","f"] | "first character" |



## Answer

```java
class Solution {
    public String solution(String[] sent) {
      	String answer = "";
      	
      	System.out.println(sent[0].substring(sent[0].indexOf(sent[1])));
      	
        return answer;
    }
}
```

### PS

java에서는 indexof()와 substring()을 사용하면 간단히 표현가능하니 편하더군요.

