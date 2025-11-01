---
title: "[Typers 팀프로젝트] React 프로젝트 세팅"
layout: post
date: 2025-04-16 16:35:59 +0900
categories: ["팀프로젝트/초기 세팅", "frontend", "react", "react 초기 세팅", "라이브러리 세팅", "폴더 구조잡기", "프론트엔드"]
tags: ["팀프로젝트/초기 세팅", "frontend", "react", "react 초기 세팅", "라이브러리 세팅", "폴더 구조잡기", "프론트엔드"]
author: "프론트 꿈나무"
original_url: "https://developer-smh.tistory.com/15"
---

드디어 이제 본격적으로 개발에 들어갈 수 있게 되었습니다!

당장 코딩부터 시작하면 좋겠지만, 그렇게 진행하게 되면  
파일 경로가 꼬인다거나, 필요한 모듈을 매번 그때그때 설치해야 되는 등의 문제가 생길 수 있습니다.

이러한 이슈를 방지하기 위해, 개발을 시작하기 전에  
폴더 구조를 미리 세팅하고, 필요한 모듈이나 라이브러리를 미리 정해서 설치하는 작업을 프로젝트 세팅이라고 하는데요?

오늘은 제 담당인 프론트쪽 프로젝트 세팅을 하는 과정을 기록하려고 합니다.

 

 

#### 프로젝트 세팅

---

#### 라이브러리 설치

---

 

#### 라우팅 (페이지 이동)

<table style="border-collapse: collapse; width: 100%; height: 38px;" border="1" data-ke-align="alignLeft" data-ke-style="style13">
<tbody>
<tr style="height: 21px;">
<td style="width: 26.4729%; height: 21px;">라이브러리</td>
<td style="width: 40.1937%; height: 21px;">설명</td>
<td style="width: 33.3333%; height: 21px;">설치 명령어</td>
</tr>
<tr style="height: 17px;">
<td style="width: 26.4729%; height: 17px; text-align: center;"><span style="background-color: #dddddd;"> react-router-dom </span></td>
<td style="width: 40.1937%; height: 17px;">SPA에서 페이지 전환을 도와주는 라우팅 라이브러리</td>
<td style="width: 33.3333%; height: 17px;"><b> npm install react-router-dom </b></td>
</tr>
</tbody>
</table>
 

상태 관리(redux)

<table style="border-collapse: collapse; width: 100%; height: 89px;" border="1" data-ke-align="alignLeft" data-ke-style="style13">
<tbody>
<tr style="height: 21px;">
<td style="width: 26.7054%; height: 21px;">라이브러리</td>
<td style="width: 39.9612%; height: 21px; text-align: center;">설명</td>
<td style="width: 33.3333%; height: 21px;">설치 명령어</td>
</tr>
<tr style="height: 17px;">
<td style="width: 26.7054%; height: 17px; text-align: center;">redux</td>
<td style="width: 39.9612%; height: 17px;">전역 상태를 예측 가능하게 관리하는 상태 관리 라이브러리</td>
<td style="width: 33.3333%; height: 17px;">npm install redux</td>
</tr>
<tr style="height: 17px;">
<td style="width: 26.7054%; height: 17px; text-align: center;">react-redux</td>
<td style="width: 39.9612%; height: 17px;">React 컴포넌트에서 Redux store를 쉽게 사용하도록 도와주는 바인딩 도구</td>
<td style="width: 33.3333%; height: 17px;">npm install react-redux</td>
</tr>
<tr style="height: 17px;">
<td style="width: 26.7054%; height: 17px; text-align: center;">redux-actions</td>
<td style="width: 39.9612%; height: 17px;">Action 생성자와 Reducer 작성을 더 간편하게 만들어주는 도우미</td>
<td style="width: 33.3333%; height: 17px;">npm install redux-actions</td>
</tr>
<tr style="height: 17px;">
<td style="width: 26.7054%; height: 17px; text-align: center;">@redux-devtools/extension</td>
<td style="width: 39.9612%; height: 17px;">Redux DevTools(크롬 확장 도구 등)와 연동해서 상태 추적을 편리하게</td>
<td style="width: 33.3333%; height: 17px;">npm install @redux-devtools/extension</td>
</tr>
</tbody>
</table>

####  

#### 스타일링

<table style="border-collapse: collapse; width: 100%; height: 34px;" border="1" data-ke-align="alignLeft" data-ke-style="style13">
<tbody>
<tr style="height: 17px;">
<td style="width: 26.5891%; height: 17px;">라이브러리</td>
<td style="width: 40.0775%; height: 17px;">설명</td>
<td style="width: 33.3333%; height: 17px;">설치 명령어</td>
</tr>
<tr style="height: 17px;">
<td style="width: 26.5891%; height: 17px;">styled-components</td>
<td style="width: 40.0775%; height: 17px;">CSS-in-JS 방식으로 컴포넌트 스타일을 작성</td>
<td style="width: 33.3333%; height: 17px;">npm install styled-components</td>
</tr>
</tbody>
</table>

####  

####  

---

#### Package.json에서 라이브러리 확인

---

![image](/assets/img/2025-04-16/img.png)

####  

####  

 

#### 폴더 구조 구성 

 

```bash
typers-client/
│
├── node_modules/              # 설치된 의존성 모듈들
├── public/                    # 정적 파일 (HTML, 이미지 등) 위치
│
├── src/                       # 소스 코드 디렉토리
│   │
│   ├── global/                # 전역 스타일 및 공통 설정
│   │   ├── common.js          # 공통 유틸리티 함수 또는 설정
│   │   ├── global.jsx         # 전역 스타일 컴포넌트
│   │   └── theme.js           # 테마 색상, 폰트 등 정의
│   │
│   ├── moduls/                # 전역상태 관리 (redux)
│   │   ├── auth.js            # 인증 관련 상태 관리
│   │   └── index.js           # 모듈 통합 및 내보내기
│   │
│   ├── pages/                 # 페이지 컴포넌트 (현재 비어 있음)
│   │
│   ├── router/                # 라우팅 관련 설정
│   │   └── router.js          # 라우트 구성 정의 파일
│   │
│   ├── App.js                 # 최상위 App 컴포넌트
│   ├── App.css                # App 컴포넌트 전용 스타일
│   ├── App.test.js            # App 테스트 파일
│   ├── index.js               # React 앱 진입점
│   ├── index.css              # 전역 스타일
│   ├── logo.svg               # React 기본 로고
│   ├── reportWebVitals.js     # 성능 측정 함수
│   └── setupTests.js          # 테스트 환경 설정
│
├── .dockerignore              # Docker 빌드 시 제외할 파일 설정
├── .gitignore                 # Git에서 제외할 파일 설정
├── Dockerfile                 # Docker 빌드를 위한 설정 파일
├── package.json               # 프로젝트 정보 및 의존성 목록
├── package-lock.json          # 정확한 의존성 버전 잠금
└── README.md                  # 프로젝트 설명 문서
```
 

#### 파일을 하나씩 살펴보는건 글이 길어지기 때문에 나눠서 준비했습니다.

[https://developer-smh.tistory.com/16](https://developer-smh.tistory.com/16)

 

 

### 끝
