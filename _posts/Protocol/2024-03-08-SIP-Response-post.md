---
title: "SIP - Response"
excerpt: "Response"
toc: true
toc_sticky: true
categories: Protocol
tags:Protocol
last_modified_at: 2024-03-08T08:17:00-18:00
---


## Response

SIP 요청에 대한 응답이 이루어져야 트랜잭션이 완료. 요청에 대한 응답이 없을 경우에는
사전 정의된 Timer까지 기다린 후에 재송신

SIP 응답은 일련 번호가 정의                      
- 1xx Provisional : 경보
- 2xx Success : 정상
- 3xx Redirection : 요청을 다른 주소로 재송신
- 4xx Client Error : 클라이언트 장애
- 5xx Server Error : 서버장애
- 6xx Global Failure : 사용자 연결은 가능하지만 통화불가


### 1xx Provisional Responses 
***
1xx Informational Responses라고도 하며 요청에 대해 최종응답전에 요청을 처리하는 시간이
200ms 이상일 때 서버가 처리중임을 통지하기 위해 발행. 
1xx 응답에는 SDP와 같은 SIP 메세지 바디가 함께 전송

- 100 Trying
  수신된 요청을 다음 서버로 전송하거나 처리 중임을 의미. 일반적으로 INVITE와 같은 요청을
  받아서 즉시 처리할 수 없을  경우에 대부분 발행.
- 180 Ringing
  UAS가 사용자에게 Alerting 중이므로 UAC에게 Ringbacktone을 재생하거나 준비할것을 통지
- 181 Call is Being Forwarded
  UAS가 착신전환되어 있으므로 현재 호가 착신전환 번호로 재시도 중임을 UAC에게 통지
- 183 Session In Progress
  진행중인 호에 대한 추가적인 정보(컬러링,부가서비스)를 전송하기 위해 사용.
- 199 Early Dialog Terminated
  RFC 6228 SIP에 새롭게 명시된 응답으로 UAS와 SIP Forking Proxy가
  최종 응답전에 다이얼로그가 종료되었음을 통지.


### 2xx Successful
***
Request가 정상적으로 처리되었음을 의미

- 200 OK
  요청을 성공적으로 처리하였음을 통지함.
- 202 Accepted
  요청은 처리를 위한 승인이 되었지만, 아직 처리중임을 통지
- 204 No Notification
  RFC 5839에 명시된 응답을 ㅗ기존 다이얼로그 내에서 SUBSCRIBE 메세지와 관련된 응답이
  보내지지 않았음을 표시.


### 3xx Redirect
***
 사용자의 새로운 위치나  UA 정보 또는 호를 위한 변경된 서비스로 응답.

- 300 Multiple Cohoices
  사용자가 여러개의 단말을 소유할 수 있음을 의미하므로 선호되는 UA로 호를 진행
- 301 Moved Permanently
  요청된 Request-URI의 주소로 단말을 찾을 수 없음을 의미. 사용자는 응답에 포함된 
  Contact Header 주소로 re-INVITE를 진행하고, Local Directories, 주소록 등에 정보를 업데이트.
- 302 Moved Temporarily
  일시적으로 다른 곳으로 이동했음을 의미. 발신자는 응답에 포함된 Contact header 주소로 
  re-INVITE를 진행. 일시적인 이동이므로 Local Directories에 업데이트할 필요 없음.
- 305 Use Proxy
  UAS에 도달한 Request가 Porxy를 경유하지 않았음을 의미. UAS는 메세지가 SIP Proxy를 
  경유하도록 Contact address를 포함.
- 380 Alternative Service
  진행중인 서비스 요청은 실패하였으나 다른 서비스는 이용 가능하다는 것을 의미.

### 4xx Request Failure
***
호의 실패를 의미하므로 실패 이유를 명기하여 응답

* 400 Bad Request
  잘못된 문구나 메세지 포맷을 따르지않아 처리될 수 없음을 의미.
  필수적인 SIP header가 빠져있을 때 발행.  
* 401 Unauthorised & 407 Proxy Authentication Required
  요청은 사용자 인증이 필요함을 의미. Registrar or UAS는 401응답을 발행하고, SIP Porxy서버는
  407 응답을 발행
- 403 Fprboddem
  서버는 Request에 대한 처리를 거절함을 의미.
- 404 Not Found
  Request-URI에 있는 도메인 주소가 존재하지 않음을 의미.
- 406 Not Acceptable
  Accept Header에 열거되지 않은 컨텐츠 타입을 요구함을 의미.
- 408 Request Timeout
  일정 시간안에 Request에 대한 응답을 할 수 없음을 의미.
- 410 Gone
  요청한 자원이 서버에서 고정적으로 이용 가능하지 않음을 의미.
- 413 Request Entity Too Large
  Request의 내용이 서버가 처리할 수 있는 것보다 너무 큼을 의미. 일시적인 상황일 경우
  Retry-After Header로 UAC가 재시도할 수 있음을 표시.
- 414 Request-URI Too Long
  Request-URI가 서버가 해석할 수 있는 길이보다 길다는 것을 의미.
- 415 Unsupported Media Type
  서버는 메세지 바디에 서버가 지원되지 않는 포맷으로 요청함을 의미. 서버는 반드시
  Accept, Accept-Encoding, Accept-Language Header 등을 이용하여 응답.
- 416 Unsuppored URI Scheme
  Request-URI 스킴을 서버가 해석할 수 없음을 의미.
- 420 Bad Extension
  서버는 Proxy-Require  or Require Header에 정의된 Extension을 이해하지 못함을 의미.
  서버는 반드시 unsuppored Header에 지원하지 않는 Extension을 명기하여 응답.
- 423 Interval Too Brief
  Request에 의해 자원을 확보하기 위한 시간이 너무 부족함을 의미.
- 480 Temporarily Unavailable
  성공적으로 연결하였지만, 현재 상대방이 응대가능하지 않음을 의미.
  ex) login은 했지만 통화가 되지않거나 Do Not Disturb 기능을 이용중일 경우
- 481 Call/Transaction Does not Exist
  UAS가 기존 다이얼로그나 트랜잭션과 매치되지 않는 요청을 받았음을 의미.
- 482 Loop Detected
  UAS가 루프 상황을 검출하였음을 의미. Via Header 값을 통해 전 서버에서 보낸 요청이
  다시 돌아 왔음을 알 수 있음.
- 483 Too Many Hops
  서버는 Max-Forwads Header 값이 0인 Request를 받았음을 의미.bbbb
- 484 Address Incomplete
  서버는 불완전한 Request-URI를 가진 Request를 받았음을 의미.
- 485 Ambiguous
  서버는 애매모호한 Reqeust-URI를 가진 Reqeust를 받았음을 의미.
- 486 Busy Here
  상대방을 성공적으로 연결하였지만, 현재 상대방이 응대가능하지 않음을 의미.
- 487 Request Terminated
  Reqeust는 BYE나 CANCEL 요청에 의해 종료되었음을 의미. CANCEL요청에 대한 응답 X
- 488 Not Acceptable Here
  Request-URI에 명기된 특정 자원이나 코덱을 사용할 수 없음을 의미.
- 491 Request Pending
  UAS는 같은 다이얼로그안에 펜딩된 요청을 가지고 있음을 의미.
- 493 Undecipherable
  Reqeust에 암호화된 MIME 바디를 포함하고 있어 처리할 수 없음을 의미. 


### 5xx Server Error
---
서버 자체가 에러가 발생하여 요청을 처리할 수 없을 때 사용.

- 500 Server Internal Error
  요청을 처리 중에 서버 내부 문제로 인해 처리할 수 없음을 의미.
- 501 Not Implementd
  요청을 처리하기 위한 서비스나 기능이 서버에서 지원되지 않음을 의미.
- 502 Bad Gateway
  게이트웨이나 Proxy서버가 잘못된 응답을 다른 서버로부터 받았음을 의미.
- 503 Service Unavailable
  서버는 일시적인 과부하나 유지보수로 인해 요청을 처리할 수 없음을 의미. 
  서버는 Retry-After header를 포함하여 응답.
- 504 Server Time-out
  서버는 외부 서버로 부터 정해진 시간 내에 응답을 받지 못했음을 의미
- 505 Version Not Supported
  서버는 SIP 프로토콜 버전을 지원하지 않음을 의미.
- 513 Message Too Long
  서버는 요청의 메세지의 길이가 너무 길어 처리할 수 없음을 의미.

### 6xx Global Failures
---
서버는 특정 사용자에 대한 최종 정보를 가지고 있다는 것을 의미

- 600 Busy Everywhere
  상대방의 단말에 연결되었지만, 상대방이 바쁘거나 전화를 받지 않아 통화할 수 없음을 의미.
- 603 Decline
  상대방의 단말에 연결되었지만, 상대방은 통화를 원하지 않음을 의미.
- 604 Does Not Exist Anywhere
  Request-URI에 나타난 사용자가 존재하지 않음을 의미.
- 606 Not Acceptable
  상대방에게 연결되었지만, 요청된 미디어나 대역폭 등의 이유로 연결할 수 없음을 의미.
