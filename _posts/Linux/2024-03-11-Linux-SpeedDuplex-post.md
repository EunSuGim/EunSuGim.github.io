---
title: "Linux - SpeedDuplex"
excerpt: "SpeedDuplex"
toc: true
toc_sticky: true
categories: Linux
tags: Linux
last_modified_at: 2024-03-11T08:17:00-18:00
---


## SpeedDuplex

- ethtool : 네트워크 장비의 인터페이스의 속도 및 통신방향을 설정해주는Linux 커널기반 OS의 유틸리티

- 통신방향성 : simplex(한방향으로만흐름 ex)라디오), Half Duplex(반 이중 전송방식 ex)무전기),  
    Full Duplex(양방향 ex)전화,LAN)

- 재부팅시에도 적용할려면  ethtool 명령어를 ifcfg-ethx파일에 추가해야함

|   |   |
|---|---|
|ethtool [인터페이스 명]|해당 인터페이스 설정 값 확인|
|ethtool –s speed [10\|100\|1000] duplex [half\|full] autoneg [on\|off]|해당 인터페이스 설정값 변경|
|ethtool –i [인터페이스 명]|해당 인터페이스 드라이버 정보 출력|
|ethtool –a [인터페이스 명]|상세 auto nego 정보 출력|

![](https://i.imgur.com/4I1zBE9.png)
