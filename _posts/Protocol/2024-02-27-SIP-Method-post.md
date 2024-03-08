---
title: "SIP - Method"
excerpt: "Method"
toc: true
toc_sticky: true
categories: Protocol
tags: SIP,Protocol
last_modified_at: 2024-02-27T08:17:00-18:00
---

## 기본 Method
***
- INVITE
  멀티미디어 세션에 참가 시키기 위한 서비스 또는 사용자를 초대하기위한 메소드
- ACK
  INVITE 메소드에 대한 최종 응답인 200OK를 수신했음을 통지하기 위한 메소드
- BYE
  기존의 세션을  종료하기 위한 메소드
- CANCEL
  최종 응답 200OK를 박기 전에 기존의 요청을 취소하기 위한 ㄷ메소드
- OPTIONS
  서버의 Capapbility를 요청하기 위한 메소드
- REGISTER
  User Agent가 Registerar Server에 등록하기 위한 메소드

## 추가 Method
***
- INFO
  깁존의 설립된 세션 또는 다이얼로그 내에서 추가적인 정보를 전송하기 위한 메소드
- PRACK
  UAC가 임시적으로 Response를 승인하기 위한 메소드
- SUBSCRIBE
  특정 이벤트를 살펴보기 위해 원격노드에 요청하기 위한 메소드
- NOTIFY
  특정 이벤트 발생 시 응답하기 위한 메소드
- UPDATE
  세션 설정 파라미터를 업데이트하기 위한 메소드
- MESSAGE
  채팅과 같은 단문 메세지를 전달하기 위한 메소드
- REFEER
  호전환과 같이 UA가 지금 통신 중인 UA 이외의 또 다른 UA와 통신하기 위한 메소드

