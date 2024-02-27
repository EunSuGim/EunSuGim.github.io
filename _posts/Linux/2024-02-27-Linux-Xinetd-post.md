---
title: "Linux - Xinetd"
excerpt: "Xinetd"
toc: true
toc_sticky: true
categories: Linux
tags: Linux
last_modified_at: 2024-02-27T08:17:00-18:00
---


## xinet

- 데몬들을 관리하는 슈퍼데몬- 데몬관리에는 2가지 방식이 존재. Standalone 방식과 Xinetd 방식- Standalone 방식은 각각의 서비스별로 데몬이 메모리에 상주하며 동작하는 방식으로  속도가 빠르나 리소스를 많이 점유한다.  
- Xinetd 방식은 슈퍼 데몬이 메모리에 상주하며 관리하는 데몬을 동작시키는 방식으로  속도는 느려지나 리소스를 절약할 수 있다.


1-1. /etc/xinetd.conf : xinetd 설정파일  
  
|   |   |
|---|---|
|log_type=SYSLOG \| FILE|로그파일을 rsyslog등 시스템 로그에서<br><br>관리되도록 위임하거나, 별도의 파일로 선택|
|log_on_failure=HOST\|USERD\|ATTEMPT|접속에 실패했을 때 기록될 값을 설정|
|log_on_success=PID\|HOST\|USERID\|EXIT\|DURATION\|TRAFFIC|접속에 성공했을 때 기록될 값을 설정|
|cps=[초당 요청 수] [제한시간]|초당 요청 수 만큼을 초과할 경우 제한시간에<br><br>설정된 초만큼 접속을 중단|
|instances= 최대 서버 수|같은 IP에서 접속할 수 있는 최대 서비스 수|
|only_form= 접속 가능한 호스트|only_form과 no_access가 중복되면 차단됨|
|no_access= 접속 불가능한 호스트|
|enabled= 사용 가능한 서비스 목록|enabled과 disabled가 중복되면 차된됨|
|disabled= 사용 불가능한 서비스 목록|


1-2. /etc/xinetd.d : 디렉터리 하위에 서비스명으로 된 설정파일을 개별 설정 가능.                  서비스명은 /etc/services 와 동일하게 설정하고 .conf는 붙이지 않는다.

|   |   |
|---|---|
|/etc/xinetd/rsync 시스템 로그설정 파일|   |
|socket_type|stream, dgram, raw 값을 지정|
|user|서비스 사용자 이름|
|wait|yes는 단일 쓰레드, no는 다중 쓰레드로 동작|
|server|서비스가 연결되었을 때 실행할 프로그램|


1-3. TCP Wrapper : /etc/hosts.deny, /etc/hosts.allow를 참조. 서비스를 전부 막고                     ssh, ftp 등 주요 서비스를 특정 호스트에만 허용해줄 수 있음.  
 - /etc/hosts.deny : 서비스별 거부 목록 파일(tcpd)  
 - /etc/hosts.allow : 서비스별 허용 목록 파일(tcpd)

1-4. 실행 / 종료 / 재시작 / 상태확인 방법- 실행 : /etc/rc.d/init.d/xinet.d [서비스 명] start    
- 종료 : /etc/rc.d/init.d/xinet.d [서비스 명] stop   
- 재시작 : /etc/rc.d/init.d/xinet.d [서비스 명] restart   
- 상태 : /etc/rc.d/init.d/xinet.d [서비스 명] status