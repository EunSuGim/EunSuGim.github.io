---
title: "Linux - RAID"
excerpt: "RAID"
toc: true
toc_sticky: true
categories: Linux
tags: RAID,Linux
last_modified_at: 2024-02-27T08:17:00-18:00
---

## RAID  
***
- Redundant Array of Independent Disks
- striping : 저장 시스템의 데이터 분산방식을 결정하며 여러 개의 디스크를 묶어 
		  하나의 디스크처럼 사용하는 기술.
- mirroring : 똑같은 데이터를 동일한 스펙의 디스크에 저장하는 방식.

### RAID Level
- RAID 0 
   1. striping방식으로 최소 2개의 디스크 필요. Raid를 구성하는 모든 디스크에 
	   데이터 분할하여 저장
   2. 성능과 용량이 N배로 좋아지지만 하나의 디스크가 장애 발생 시 전체가 장애.
	![](https://i.imgur.com/HEnIgOC.png)

- RAID 1
   1. mirroring 방식으로 최소 2개 디스크 필요. 한 쪽 디스크에 데이터를 그대로 복사하여 
	      다른 디스크에서 장애발생시 파일 유지가능하지만 비용이 많이 비싸고 속도가느림. 

	![](https://i.imgur.com/vXzTTP9.png)

- RAID 5
  1. HDD1 받침대부분의 용량의 Parity라고 불리는 데이터를 항상 부가하고 보존하는것으로
	     한 쪽 HDD가 고장날 떄에도 잃어버린 부분의 데이터를 Parity로부터 생성 가능
  2. Parity는 HDD에 장애가 발생한 뒤에 데이터를 복원하기 위해 사용되는 부호
	     RAID에 데이터를 쓸때 자동적으로 생성. 남아있는 데이터와 조합하여 데이터를 복구
  3. 1대의 HDD가 깨진 상태에서도 가동가능하므로 고장내성에 강하지만 CPU에 부하가걸림.
	![](https://i.imgur.com/JCd8QBz.png)

- RAID 6
  1. Parity를 이중 생성하여, 다른 디스크에 기록하는것으로 의해 안정성 향상하지만
	     생성되는 Parity 증가로 성능이나 용량 효율이 안좋음.
	![](https://i.imgur.com/wbZEf3b.png)

- RAID 10
  1. RAID 1과 RAID 0를 조합한 RAID 방식.
  2. 데이터 속도와 안정성이 높아지는 대신 비용적 측면 증가.
	![](https://i.imgur.com/tEJThFN.png)
