---
title: "Web - Virtualization"
excerpt: "Virtual"
toc: true
toc_sticky: true
categories: web
tags: web, Virtual
last_modified_at: 2024-02-27T08:17:00-18:00
---

## Virtualization
***
 - HOST OS 필요없이 직접 H/W에 설치하여 Guest Os를 구동시키는 방식
 - 관리 콘솔 필요(EXSI) 호스트 가상화에 비해 오버헤드가 적음
 - 전가상화, 반가상화로 구분

![](https://i.imgur.com/MA8LabW.png)

***
## 전가상화(Full Virtualization)

 - H/w를 완전히 가상화하는 방식 Hardware Virtual Machine
 - hypervisor가 하드웨어 접근을 전부 제어하기 때문에 GuestOS는 hypervisor의 존재를 몰라도됨.
 - GuestOS는 커널 등 수정이 필요없어 다양한 OS 사용가능
 - hypervisor가 GuestOS의 명령어를 처리해야하고 각 OS종류가 다를 수 있기 때문에
   Binary Translation 작업이 필요함으로써 오버헤드가 발생하거나 속도가 느려질 수 있다. 

***
## 반가상화(Para Virtualization)

 - 전가상화의 문제점을 해결하고자 만들어진 방식
 - Hyper Call이라는 인터페이스를 통해 특정 명령어를 Hypervisor에 직접 요청
 - 중요한 명령어만 Hypervisor에게 요청하므로 전가상화보다 오버헤드가 적고 성능이 개선

 - GuestOS는 명령어를 구분해야하기 때문에 커널을 수정하여 Guest용 OS를 따로만들어야함
 ***
