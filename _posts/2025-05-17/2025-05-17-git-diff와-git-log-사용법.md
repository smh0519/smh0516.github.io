---
title: "git diff와 git log 사용법"
layout: post
date: 2025-05-17 13:28:19 +0900
categories: ["Git&amp;GitHub/기본 명령어", "Git", "git diff", "git log", "git 기록 확인"]
tags: ["Git&amp;GitHub/기본 명령어", "Git", "git diff", "git log", "git 기록 확인"]
author: "프론트 꿈나무"
original_url: "https://developer-smh.tistory.com/21"
---

지난 글에서는 Git 저장소를 만들고,  
변경 내용을 스테이징하고 커밋하는 방법을 알아봤죠?

이번에는 그렇게 기록된 내용들을 어떻게 확인하고 추적하는지 알아볼 차례입니다.

git diff와 git log를 활용해서 변경 내역을 분석하는 방법, 함께 살펴보겠습니다!

 

---

## 변경 사항 추적 -  git diff

---

기능:

git diff는 Git 저장소에서 두 지점 사이의 차이점(diff) 을 보여주는 명령어입니다. 일반적으로는 파일 내용의 줄 단위 변경 사항을 확인하는 데 사용됩니다.

 

Git에는 크게 세 가지 작업 영역이 존재합니다:

- Working Directory (작업 디렉토리): 현재 내가 편집하고 있는 실제 파일들

- Staging Area (인덱스): 커밋하기 위해 선택한 파일 상태

- Repository (HEAD): 마지막 커밋된 상태

 

주요 비교 유형 

#### 1. git diff

  ৹   작업 디렉토리 vs 스테이징 영역의 차이를 보여줍니다.

  ৹    즉, 아직 git add 하지 않은 변경사항을 볼 수 있습니다.

 

명령어

> git diff

 

 언제 사용할까?

→ 파일을 수정한 뒤, 커밋하기 전에 어떤 내용이 바뀌었는지 확인하고 싶을 때

 

 

#### 2.  git diff --staged

  ৹   스테이징 영역 vs HEAD(마지막 커밋) 의 차이를 보여줍니다.

  ৹    즉, 커밋될 준비가 된 변경사항을 볼 수 있습니다.

 

명령어

> git diff --staged

 

 언제 사용할까?

→ git add로 올려놓은 변경사항이 정확히 무엇인지 커밋 전에 확인할 때

 

 

#### 3.  git diff HEAD

  ৹    작업 디렉토리 전체 vs HEAD(마지막 커밋) 의 차이를 보여줍니다. 

  ৹    즉, 아직 커밋되지 않은 모든 변경사항을 한 번에 확인할 수 있습니다.

 

명령어

> git diff HEAD

 

 

 언제 사용할까?

→ 현재 작업 중인 모든 변경사항(스테이징 여부와 관계없이)을 통합적으로 보고 싶을 때

 

 

 

---

#### 요약

<table style="border-collapse: collapse; width: 99.8835%; height: 73px;" border="1" data-ke-align="alignLeft" data-ke-style="style12">
<tbody>
<tr style="height: 17px;">
<td style="width: 33.3333%; height: 17px; text-align: center;">명령어</td>
<td style="width: 33.3333%; height: 17px; text-align: center;">비교대상</td>
<td style="width: 35.7371%; height: 17px; text-align: center;">용도</td>
</tr>
<tr style="height: 20px;">
<td style="width: 33.3333%; height: 20px; text-align: center;">git diff</td>
<td style="width: 33.3333%; height: 20px; text-align: center;">작업 디렉토리 ↔ 스테이징</td>
<td style="width: 35.7371%; height: 20px; text-align: center;">수정했지만 add 하지 않은 변경사항 보기</td>
</tr>
<tr style="height: 10px;">
<td style="width: 33.3333%; height: 10px; text-align: center;">git diff --staged</td>
<td style="width: 33.3333%; height: 10px; text-align: center;">스테이징 ↔ HEAD</td>
<td style="width: 35.7371%; height: 10px; text-align: center;">add된 변경사항이 커밋과 어떻게 다른지 보기 </td>
</tr>
<tr style="height: 26px;">
<td style="width: 33.3333%; height: 26px; text-align: center;">git diff HEAD</td>
<td style="width: 33.3333%; height: 26px; text-align: center;">작업 디렉토리 ↔ HEAD</td>
<td style="width: 35.7371%; height: 26px; text-align: center;">전체 변경사항 한 번에 보기</td>
</tr>
</tbody>
</table>
 

 

이해를 돕기 위한 이미지

![image](/assets/img/2025-05-17/img.png)

---

## 커밋 기록 보기 -  git log

---

기능:

git log는 Git 저장소에서 이루어진 모든 커밋의 이력(history) 을 확인할 수 있는 기본 명령어입니다.

이 명령어를 사용하면, 개발자가 어떤 변경을 언제, 누가, 어떤 메시지와 함께 커밋했는지에 대한 정보를 시간순으로 볼 수 있습니다.

 

####  1. git log 기본 정보

- 커밋 해시 (commit ID): 해당 커밋을 식별하는 고유한 SHA 값

- 작성자(author): 커밋을 만든 사람

- 날짜(date): 커밋이 작성된 시간

- 커밋 메시지: 커밋의 내용을 설명한 요약 메시지

 

명령어

> git log

 

예시 출력

![image](/assets/img/2025-05-17/img.png)

 

 

언제사용할까?

 

- 누가 어떤 코드를 작성했는지 추적할 때

- 최근 변경 사항을 확인하고 싶을 때

- 특정 커밋을 찾아서 체크아웃하거나 되돌릴 때

 

 

#### 2.  git log --oneline 

  ৹  각 커밋을 한 줄로 요약해서 출력

  ৹  커밋 ID(짧은 SHA) + 커밋 메시지만 보기 

  ৹  복잡한 히스토리를 빠르게 파악할 때 유용

 

명령어

> git log --oneline  
  
  
출력예시  
a1b2c3d 로그인 기능 구현   
d4e5f6g 회원가입 폼 수정 

 

 

 

---

## 마무리

---

 

> 이번 글에서는 Git에서 변경 사항을 추적하고 기록을 확인하는 데 유용한 git diff와 git log 명령어를 살펴봤습니다.

이 두 명령어만 잘 활용해도, 협업 중 어떤 변경이 있었는지 파악하고, 코드 히스토리를 명확히 이해하는 데 큰 도움이 됩니다.

다음 글에서는 브랜치(branch) 개념과 함께, 커밋 히스토리를 더 자유롭게 관리하는 방법을 다뤄보겠습니다.
