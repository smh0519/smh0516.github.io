---
title: "Coalescing: 인접한 가용 블록 병합 알고리즘"
layout: post
date: 2025-10-29 22:48:26 +0900
categories: []
tags: []
author: "프론트 꿈나무"
original_url: "https://developer-smh.tistory.com/44"
---

### Coalesce() 함수 사용이유

 

- malloc에서 메모리를 반복적으로 할당/해제하다 보면,  
메모리가 조각조각 나뉘는 외부 단편화(external fragmentation)가 발생한다.

- 이 문제를 해결하기 위해 free 블록들을 합쳐주는 과정이 필요한데,  
그 역할을 하는 함수가 바로 coalesce()이다.

 

 

### 4가지 병합 케이스별 시각적 설명

 

![image](/assets/img/2025-10-29/img.png)

 

 

#### Case 1️⃣ : 앞, 뒤 모두 할당된 경우

- 병합할 블록이 없음 → 그대로 반환

- return bp

#### Case 2️⃣ : 앞은 할당, 뒤는 가용

- 현재 블록과 뒤 블록 병합

- 크기를 더하고, header/footer 업데이트

#### Case 3️⃣ : 앞은 가용, 뒤는 할당

- 앞 블록과 현재 블록 병합

- bp를 PREV_BLKP(bp)로 옮기는 이유 강조

#### Case 4️⃣ : 앞, 뒤 모두 가용

- 세 블록을 모두 합쳐서 하나로

- header는 앞 블록에, footer는 뒤 블록에 기록

 

 

 

 

 

 

 

 

 

### 코드 설명

![image](/assets/img/2025-10-29/img.png)
