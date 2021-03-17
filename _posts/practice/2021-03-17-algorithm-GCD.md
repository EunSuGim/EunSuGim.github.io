---
title: "Algorithm - GCD"
excerpt: "Algorithm"
toc: true
toc_sticky: true
categories: algorithm
tags: Practice
last_modified_at: 2021-03-17T08:17:00-18:00
typora-root-url: ..\..\assets\img\Algorithm
---

## Question
최대 공약수를 구하시오.

 ※ 제한사항

- 유클리드 호제법을 사용.



## Input / Output

| phone_book | return |
| ---------- | ------ |
| [12,24]    | 12     |
| [18,10]    | 2      |



## Answer

처음에는 호제법이 무엇인지 안알아보고 생각나는대로 작성했습니다.

```java
class Solution {
    public int solution(int num1, int num2) {
        int answer = 0;
        int tmp = 0;
        if(num2 > num1) {
        	tmp = num2;
        	num2 = num1;
        	num1 = tmp;
        }
        
        for(int i=2;i<num1;i++) {
        	if(i > num2 ) break;
        	if(num1%i==0) {
        		if(num2%i==0 && i > answer) {
        			answer = i;
        		}
        	}
        }
        
        return answer;
    }
}
```

그 후 호제법을 보고 코드를 다시 짰습니다.

```java
class Solution {
    public int solution(int num1, int num2) {
        int answer = 0;
        int tmp = 0;
               
        while(num2!=0) {
        	tmp = num1 % num2;
        	num1 = num2;
        	num2 = tmp;
        }
        
        answer = num1;
        
        return answer;
    }
}
```



### PS

확실히 호제법을 사용한게 가독성도 좋고 코드도 짧아지네요.
주구장창 코딩하는것보다 수학공부하는게 더 도움될 수 도 있겠다십네요.