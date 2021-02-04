---
title: "Exercise - Marathon"
excerpt: "Exercise"
toc: true
toc_sticky: true
categories: Exercise
tags: Practice
last_modified_at: 2021-02-04T08:17:00-18:00
typora-root-url: ..\..\assets\img\Exercise
---

## Question
수많은 마라톤 선수들이 마라톤에 참여하였습니다. 단 한 명의 선수를 제외하고는  
모든 선수가 마라톤을 완주하였습니다.  
마라톤에 참여한 선수들의 이름이 담긴 배열 participant와 완주한 선수들의   
이름이 담긴 배열 completion이 주어질 때  
완주하지 못한 선수의 이름을 return 하도록 solution 함수를 작성해주세요. 

 ※ 제한사항

- 참여선수는 1명이상입니다.
- completion의 길이는 participant의 길이보다 1작습니다.
- 참가자의 이름은 1개 이상 20개 이하의 알파벳 소문자입니다.
- 참가자 중에는 동명이인이 있을 수 있습니다.

## Input / Output

| participant                             | completion                       | return |
| --------------------------------------- | -------------------------------- | ------ |
| [leo, kiki, eden]                       | [eden, kiki]                     | leo    |
| [marina, josipa, nikola, vinko, filipa] | [josipa, filipa, marina, nikola] | vinko  |
| [mislav, stanko, mislav, ana]           | [stanko, ana, mislav]            | mislav |



## Answer

```java
import java.util.HashMap;
import java.util.Map.Entry;

class Solution {
    public String solution(String[] participant, String[] completion) {
        String answer = "";
        HashMap<String,Integer> map = new HashMap<String,Integer>();
        
        for(String part : participant) {
        	map.put(part,map.getOrDefault(part, 0)+1);
        }
        
        for(String comp : completion) {
        	map.put(comp,map.get(comp)-1);
        }
        
        for(Entry<String,Integer> entry : map.entrySet()) {
        	if(entry.getValue()>0) {
        		answer = entry.getKey();
        		break;
        	}
        }
                
        return answer;
    }
}
```

