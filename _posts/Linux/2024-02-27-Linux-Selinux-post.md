---
title: "Linux - Selinux"
excerpt: "Selinux"
toc: true
toc_sticky: true
categories: Linux
tags: Linux
last_modified_at: 2024-02-27T08:17:00-18:00
---


## Selinux

- Security-Enhanced Linux라고 하며 보안 정책을 강화시켜 접근 권한에 대해 쉽게  제어하지 못하도록 관리하는 보안 모듈

3.1 Selinux 비활성화 방법 - 활성화 여부 확인방법 : getenforce, sestatus  
 - 비활성화   1. /etc/sysconfig/selinux 파일 열기(CentOS 7.x이후 버전은 /etc/selinux/config)  
   2. SELINUX=enforcing -> disabled로 변경   3. reboot

 - Selinux 해제 후 다시 실행할 경우 relabel이 필요하며 잘못된 설정이 있을 경우   부팅이 안되거나 ssh로 원격 접속이 불가능할 수 있으므로 permissive로 설정 후 재부팅

4. Iptables

- 리눅스 패킷 필터링도구로 방화벽 설정이나 NAT에 사용(CentOS 7.x이후엔 firewalld사용)

4.1 비활성화 방법

|                                   |                          |
| --------------------------------- | ------------------------ |
| service iptables stop             | reboot시 재활성화             |
| /etc/init.d/iptables start        |                          |
| chkconfig –level 345 iptables off | runlevel 3,4,5에서 비활성화    |
| iptables –F                       | 방화벽 설정 초기화               |
| iptables –L                       | 방화벽에서 동작하고 있는 서비스 확인 명령어 |
