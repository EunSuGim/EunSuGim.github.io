---
title: "Linux - Bonding"
excerpt: "Bonding"
toc: true
toc_sticky: true
categories: Linux
tags:Linux,Bonding
last_modified_at: 2024-03-08T08:17:00-18:00
---


## Bonding

- 여러 개의 물리적 NIC을 논리적으로 묶어 확장하거나 다른 장치에 장애가 생겼을 때  
이중화 작업으로 서비스를 중단없이 사용하기위함

- /etc/sysconfig/network-scripts/Bond0 설정파일

  BONDING_MASTER= bonding장치로 동작 여부

  BONGIND_OPTS = “mode=1 miimon=100” 본딩옵션

![](https://i.imgur.com/JWO69xa.png)


- Bonding mode

|   |   |   |
|---|---|---|
|mode|명칭|설명|
|0|balance-RR|디폴트값. round-robin방식. 모든 slave장치를 차례로 패킷전송|
|1|active-backup|하나의 NIC 장치만 Active, Active interface 만 패킷 송수신|
|2|balance-xor|Load balancing(xor). 송수신양쪽 MAC 바탕으로 전송slave 결정|
|3|broadcast|모든 slave에 동일한 패킷전송|
|4|802.3ad|IEEE 802.3ad dynamic link aggregation. 송수신 패킷 분산|
|5|balance-tlb|Transmit Load Balancing. 각 slave의 부하에 따라 전송 slave 분산|
|6|balance-alb|Adaptive Load Balancing. mode5기능과 송수신 패킷 부하분산|

- /etc/sysconfig/network-scripts/ifcfg-ens256 설정파일
MASTER = bonding에 귀속 SLAVE = MASTER에 구성맴버로 동작할지 여부

CSCF bonding
[root@pcscf1a:/etc/sysconfig/network-scripts ] grep bond0 ifcfg*

ifcfg-bond0:NAME=bond0

ifcfg-bond0:DEVICE=bond0

ifcfg-p1p1:MASTER=bond0

ifcfg-p2p1:MASTER=bond0

[root@pcscf1a:/etc/sysconfig/network-scripts ] cat ifcfg-bond0

BOOTPROTO=none

NAME=bond0

BONDING_OPTS="mode=1 miimon=100"

IPADDR=183.114.49.137

NETMASK=255.255.255.224

GATEWAY=183.114.49.129

DEVICE=bond0

ONBOOT=yes

[root@pcscf1a:/etc/sysconfig/network-scripts ] cat ifcfg-p1p1

TYPE=Ethernet

PROXY_METHOD=none

BROWSER_ONLY=no

BOOTPROTO=none

DEFROUTE=yes

IPV4_FAILURE_FATAL=no

IPV6INIT=yes

IPV6_AUTOCONF=yes

IPV6_DEFROUTE=yes

IPV6_FAILURE_FATAL=no

IPV6_ADDR_GEN_MODE=stable-privacy

NAME=p1p1

UUID=d7db3aaf-a5b4-4545-9895-f7b8912ba9dd

DEVICE=p1p1

ONBOOT=yes

MASTER=bond0

SLAVE=yes

[root@pcscf1a:/etc/sysconfig/network-scripts ] cat  ifcfg-p2p1

TYPE=Ethernet

PROXY_METHOD=none

BROWSER_ONLY=no

BOOTPROTO=none

DEFROUTE=yes

IPV4_FAILURE_FATAL=no

IPV6INIT=yes

IPV6_AUTOCONF=yes

IPV6_DEFROUTE=yes

IPV6_FAILURE_FATAL=no

IPV6_ADDR_GEN_MODE=stable-privacy

NAME=p2p1

UUID=94131587-5452-4a51-b8f7-1eb8c3d1d712

DEVICE=p2p1

ONBOOT=yes

MASTER=bond0

SLAVE=yes
