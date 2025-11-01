---
title: "Git &amp; GitHub 입문 가이드"
layout: post
date: 2025-05-08 18:54:33 +0900
categories: ["Git&amp;GitHub", "Git", "git&amp;github차이점", "GitHub", "Github란?", "git란?"]
tags: ["Git&amp;GitHub", "Git", "git&amp;github차이점", "GitHub", "Github란?", "git란?"]
author: "프론트 꿈나무"
original_url: "https://developer-smh.tistory.com/19"
---

개발을 하다 보면 한 번쯤은 Git과 GitHub라는 단어를 들어보셨을 겁니다.  
하지만 이게 정확히 무엇을 하는 도구인지, 어떤 차이가 있는지 헷갈리는 분들도 계실 텐데요.

이번 글에서는 Git과 GitHub가 무엇인지, 각각 어떤 역할을 하는지에 대해 간단하고 쉽게 설명해드리겠습니다.

 

---

## Git이란?

---

>  Git은 소스코드를 버전별로 관리할 수 있는 도구입니다

##  

###  Git의 주요 역할  
  

 

1. 버전 관리   
 Git은 파일의 변경 내역을 스냅샷으로 저장합니다.  각 변경은 commit이라는 단위로 저장되며, 언제 어떤 변경이 있었는지 추적   가능합니다. 또한 실수로  코드를 망가뜨렸을 때, 이전 상태로 되돌리기(revert) 할 수 있어요.

>   예: 5일 전의 코드로 돌아가서 다시 작업할 수 있음

 

 

 

2. 분산 저장  
Git은 로컬 저장소(Local Repository) 개념이 있어 인터넷 없이도 거의 모든 작업이 가능합니다.

>  인터넷 없이도 commit,branch,merge 가능. GitHub은 그 저장소를 인터넷에 올리는 용도

 

 

 3. 협업 지원  
Git은 여러 개발자가 동시에 작업할 수 있게 해주는 브랜치(branch) 기능이 핵심입니다.  각자 다른 브랜치에서 작업하다가, 나중에 병합(merge) 가능.

>   팀원이랑 충돌 없이 병렬로 작업 가능

 

 

 

4. 이력 추적 및 책임 명확화 

 누가 ,언제 ,어떤 코드를 변경했는지 정확히 기록되고, 각 commit은 고유한 ID(해시값)를 가지며, 메시지로 변경 이유도 남김

 

---

## GitHub란?

---

>  GitHub는 Git 저장소를 인터넷에서 관리할 수 있도록 해주는 서비스입니다. 

 

 

### GitHub의 주요 역할

 

1. Git 저장소를 온라인에 백업 및 공유  
GitHub는 Git 저장소를 인터넷에 업로드(push)해서 저장합니다. 덕분에 로컬 컴퓨터가 고장 나도, 코드가 안전하게 보존돼요. 다른 사람과 링크만 공유하면 누구나 내 코드를 볼 수 있어요.

> ✅ 역할 : 코드 백업 + 공유

 

 

2.  협업과 팀 개발을 쉽게 만들어줌

Pull Request (PR): 팀원이 작성한 코드를 저장소에 반영하기 전에 검토/토론 가능  
Branch 기반 작업 : 각자 다른 브랜치에서 기능을 만들고 PR로 병합  
Review 기능: 코드에 직접 댓글 달아서 피드백 가능

Merge 관리: 자동 병합 + 충돌 표시 제공

> ✅ 역할 : 팀 협업 구조화 및 코드 리뷰 프로세스 지원

 

 

3.  이슈 관리 (Issue Tracker)

버그, 할 일 목록, 기능 제안 등을 Issue로 기록하고 추적할 수 있음.   
라벨, 마일스톤, 할당 등을 통해 프로젝트 관리도 가능

> ✅ 역할: 업무 관리 & 소통

 

 

4. CI/CD 및 자동화 기능

테스트, 빌드, 배포 등 자동화 워크플로를 설정 가능.

코드를 push할 때마다 자동으로 테스트 실행 가능

> ✅ 역할:   
자동화된 개발 파이프라인 구성

 

 

 

 

 

---

## Git과 GitHub의 관계 정리

---

<table style="border-collapse: collapse; width: 100%; height: 73px;" border="1" data-ke-align="alignLeft" data-ke-style="style13">
<tbody>
<tr style="height: 22px;">
<td style="width: 15.31%; height: 22px; text-align: center;"><b>항목</b></td>
<td style="width: 37.9845%; height: 22px; text-align: center;"><b>Git</b></td>
<td style="width: 46.7054%; height: 22px; text-align: center;"><b>GitHub</b></td>
</tr>
<tr style="height: 17px;">
<td style="width: 15.31%; height: 17px; text-align: center;">용도</td>
<td style="width: 37.9845%; height: 17px; text-align: left;">버전 관리 도구</td>
<td style="width: 46.7054%; height: 17px; text-align: left;">Git 저장소 호스팅 및 협업 플랫폼</td>
</tr>
<tr style="height: 17px;">
<td style="width: 15.31%; height: 17px; text-align: center;">위치</td>
<td style="width: 37.9845%; height: 17px; text-align: left;">로컬 (PC 내부)</td>
<td style="width: 46.7054%; height: 17px; text-align: left;">클라우드 (온라인)</td>
</tr>
<tr style="height: 17px;">
<td style="width: 15.31%; height: 17px; text-align: center;">기능</td>
<td style="width: 37.9845%; height: 17px; text-align: left;">commit, branch, merge 등</td>
<td style="width: 46.7054%; height: 17px; text-align: left;">Pull Request, Issue, Actions, CI/CD 등</td>
</tr>
<tr>
<td style="width: 15.31%; text-align: center;">필요 여부</td>
<td style="width: 37.9845%; text-align: left;">필수</td>
<td style="width: 46.7054%; text-align: left;">선택 (협업하려면 매우 유용)</td>
</tr>
<tr>
<td style="width: 15.31%; text-align: center;">인터넷 필요 여부</td>
<td style="width: 37.9845%; text-align: left;"> 필요 없음 ❌</td>
<td style="width: 46.7054%; text-align: left;">필요함 <span style="color: #333333; text-align: left;">✅<span> </span></span></td>
</tr>
</tbody>
</table>
