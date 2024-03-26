---
title: "Linux - YumRpm"
excerpt: "YumRpm"
toc: true
toc_sticky: true
categories: Linux
tags: Linux
last_modified_at: 2024-03-19T08:17:00-18:00
---


## Yum과 Rpm


- rpm : RedHat Package Manager의 약자. 패키지를 자동으로 설치(windows setup.exe)  
- 컴퓨터에 패키지가 있다면 인터넷연결없이도 설치가능.  
- 패키지의 의존성 문제를 해결해주지않음.  
- rpm 파일명 규칙 [mysql-connector-java]-[5.1.25]-[3].[el7].[noarch].rpm 패키지명-소스버젼-릴리즈버전.OS버전.아키택쳐(CPU)

- yum : rpm의 패키지 의존성 문제를 해결하기위해 개발된 도구(Yellodog Updater Modified)  
- 기본적으로 인터넷이 연결되어있어야함.  
- 최종적으로 필요한 의존 패키지들을 자동으로 설치- 인터넷으로 연결된 저장소에 없는 패키지들은 설치 불가- CentoOS 6.x 버전은 공식지원종료이기 때문에 yum을 사용할려면 별도 작업필요

1.1 rpm, yum 기본 명령어

 - rpm 기본 명령어 : rpm [option] [package name]

|                  |                                           |
| ---------------- | ----------------------------------------- |
| rpm –qa package  | 설치여부 조회                                   |
| rpm –Uvh package | 설치 : U(설치된경우 업그레이드), v(설치과정 출력), h(진행률출력) |
| rpm –e package   | 패키지 삭제                                    |

 - yum 기본 명령어 : yum [option] [command] [package name]

|   |   |
|---|---|
|yum search package|패키지 검색|
|yum –y install package|설치중간 yes/no 여부에 전부 y처리하고 설치|
|yum localinstall package|rpm파일에 의존성있는 파일 자동으로 설치|
|yum remove package|패키지 삭제|

1.2 CentOS 6.x 버전대에서 yum 사용방법

 - mirror.centos.org 링크가 작동하지않아 /etc/yum.repos.d/CentOS-Base.repo 파일안에   base, updates, extras하위 baseurl=https://vault.centos.org/6.10/os/x86_64/ url수정 - /etc/yum/pluginconf.d/fastestmirror.conf 에서 enabled=0으로 수정

1.3 로컬에서 yum 사용 설정 방법 - CentOS iso파일을 업로드 후 mount :

|   |   |
|---|---|
|mkdir local_repo|mount할 폴더생성|
|mount –o loop Cent~.iso /home/local_repo|해당 OS의 iso파일을 –o loop으로 마운트|
|vi /etc/yum.repos.d/local.repo|local.repo파일에 name,baseurl,enabled,gpgcheck 설정 후 저장|
|yum clean all|yum 캐시삭제|
|yum repolist|yum local-repo 확인|

 ![](https://i.imgur.com/ZgvKHPU.png)
![](https://i.imgur.com/3NGTmxh.png)


