---
title: "Diameter - Method"
excerpt: "Method"
toc: true
toc_sticky: true
categories: Protocol
tags: Diameter, Protocol
last_modified_at: 2024-03-08T08:17:00-18:00
---


## UAR
***
- User Authorization Request
- IMS 서비스를 이용하기 위해 가입자 권한정보를 요청하는 메시지 
- S-CSCF가 미할당 상태에서 S-CSCF Selection을 위한 SCSCF Capa정보 제공
- S-CSCF가 할당 된 상태에서는 S-CSCF Name 제공
![](https://i.imgur.com/zfkw6xc.png)


***
## MAR
***
- Multimedia Authentication Request
- 가입자 인증을 수행하기 위해, 인증 벡터를 요청하는 메시지
- 실제 가입자 인증은 단말과 S-CSCF 간 인증 수행을 한다.
- MAR 메시지 (S-CSCF -> HSS)
![](https://i.imgur.com/mPBqODz.png)

![](https://i.imgur.com/t8jHxZ3.png)


***
## SAR
***
- Server Assignment Request
- 해당 가입자에 S-CSCF 주소 할당 및 해제를 요청하는 메시지
- HSS는 SAR 메시지의 SA type에 따라 가입자 상태 및 S-CSCF 주소를 등록한다
![](https://i.imgur.com/yyT1v6N.png)

![](https://i.imgur.com/lXU1vuk.png)

![](https://i.imgur.com/EBwCWRB.png)


***
## LIR
***
- Location Information Request
- 착신 가입자의 위치 질의 요청 메시지(SIP Invite 메시지, I-CSCF -> HSS)
- 
![](https://i.imgur.com/GjTdrNv.png)


***
## RTR
***
- Registration Termination Request
![](https://i.imgur.com/onwE49E.png)


***
## PPR
***
- Push Profile Request
![](https://i.imgur.com/HNscJqP.png)

