---
title: "Linux - Route"
excerpt: "Route"
toc: true
toc_sticky: true
categories: Linux
tags:Linux, Route
last_modified_at: 2024-03-08T08:17:00-18:00
---


#Route
- route 명령어로 add 할 시 재부팅할 때 초기화됨.

- 재부팅시에도 적용할려면 route 명령어를 ifcfg-ethx파일에 추가해야함

|   |   |
|---|---|
|-route add –net x.x.x.x netmask 255.255.255.255 dev ethx|단일 네트워크 추가|
|-route add –net x.x.x.0 netmask 255.255.255.0 dev ethx|대역 네트워크 추가|
|-route add –host x.x.x.x dev ethx|호스트 추가|
  
![](https://i.imgur.com/7XZNArr.png)


※ifcfg 설정파일 관련

|   |   |
|---|---|
|DEVICE=|디바이스명|
|HWADDR=|MAC주소|
|TYPE=|Ethernet에 대한 설정|
|UUID=|고유ID 자동부여|
|IPV6INIT=|IPV6 사용여부|
|USERCTL=|일반사용자의 eth0제어 가능여부|
|ONBOOT=|시스템시작시 자동활성화 여부|
|BOOTPROTO=|IP부여방식, static, DHCP 결정|
|IPADDR=|IP주소지정|
|NETMASK=|서브넷 지정|
|GATEWAY=|게이트웨이 지정|
|ETHTOOL_OPTS=|speed duplex 설정|
