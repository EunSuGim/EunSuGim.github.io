---
title: "Algorithm - Running"
excerpt: "Algorithm"
toc: true
toc_sticky: true
categories: algorithm
tags: Practice
last_modified_at: 2024-03-07T08:17:00-18:00
typora-root-url: ..\..\assets\img\Algorithm
---

## Question
얀에서는 매년 달리기 경주가 열립니다. 해설진들은 선수들이 자기 바로 앞의 선수를 추월할 때 추월한 선수의 이름을 부릅니다. 
예를 들어 1등부터 3등까지 "mumu", "soe", "poe" 선수들이 순서대로 달리고 있을 때,
해설진이 "soe"선수를 불렀다면 2등인 "soe" 선수가 1등인 "mumu" 선수를 추월했다는 것입니다. 즉 "soe" 선수가 1등, "mumu" 선수가 2등으로 바뀝니다.

선수들의 이름이 1등부터 현재 등수 순서대로 담긴 문자열 배열 players와 해설진이 부른 이름을 담은 문자열 배열 callings가 매개변수로 주어질 때, 경주가 끝났을 때 선수들의 이름을 1등부터 등수 순서대로 배열에 
담아 return 하는 solution 함수를 완성해주세요.



## Input / Output

players  
["mumu", "soe", "poe", "kai", "mine"]
callings  
["kai", "kai", "mine", "mine"]
result  
["mumu", "kai", "mine", "soe", "poe"]


## Answer

```java
import java.util.stream.IntStream;
import java.util.Map;
import java.util.stream.Collectors;
import java.util.Collections;
import java.util.function.Function;
class Solution {
    public String[] solution(String[] players, String[] callings) {
       Map<String,Integer> map = IntStream.range(0,players.length)
           .boxed()
           .collect(Collectors.toMap(i->players[i], Function.identity()));
        
        for(String calling : callings){
            int idx = map.get(calling);
            String tmp = players[idx-1];
            players[idx-1] = players[idx];
            players[idx] = tmp;
            
            map.put(players[idx],idx);
            map.put(players[idx-1],idx-1);
            
        }
        
        return players;
    }
}
```



### PS

Stream을 처음 써보는데 좀 더 다뤄봐야겠습니다. 많이 유용하네요.