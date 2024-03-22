---
title: "Linux - chkconfig"
excerpt: "chkconfig"
toc: true
toc_sticky: true
categories: Linux
tags: Linux
last_modified_at: 2024-02-27T08:17:00-18:00
---


## chkconfig

- 시스템 부팅시 실행될 데몬 설정을 하는 유틸리티.
- 부팅 시 데몬 리스트와 runLevel 별 실행여부확인 및 설정
- windows의 시작프로그램과 같은 역할

### Run Level

- 리눅스 시스템에서 0~6단계를 구성하여 부팅 시 제공되는 서비스수준을 나타낸다.

| Run Level | Description                                            |
| --------- | ------------------------------------------------------ |
| 0         | Hat : 시스템 종료                                           |
| 1         | Single user mode : 관리자권한, 시스템 점검 및 복원                  |
| 2         | Multi-user mode(without network) : 다중 사용자 모드(네트워크 미지원) |
| 3         | Full Multi-user mode : 일반적인 다중 사용자 모드, CLI             |
| 4         | Notused : 사용하지않는 run level이고, 임의로 정의해서 사용가능            |
| 5         | Full Multi-user mode : run level 3와 같지만 GUI            |
| 6         | Reboot : 시스템 재부팅                                       |


1-1. 명령어

|   |   |
|---|---|
|chkconfig --list [데몬 명]|데몬의 런레벨 상태 확인|
|chkconfig --add [데몬 명]|데몬 추가|
|chkconfig --del [데몬 명|데몬 삭제|
|chkconfig [--level] [데몬 명] [on\|off\|reset]|데몬 레벨 별 설정(런레벨 미입력시 2~5 적용)|

1-2. 디렉터리  
- chkconfig의 데몬들의 스크립트 경로 : /etc/rc.d/init.d  현재 시스템에서 chkconfig 명령 수행 시 출력되는 데몬들의 스크립트 해당 경로에서  스크립트 등록  
- /etc/rc.d/경로에는 각 Run Level마다 디렉터리로 구분