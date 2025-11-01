---
title: "[Typers 팀프로젝트] react src폴더 구성"
layout: post
date: 2025-04-18 09:00:38 +0900
categories: ["팀프로젝트/초기 세팅", "frontend", "react", "react폴더 구성", "팀프로젝트", "프론트엔드"]
tags: ["팀프로젝트/초기 세팅", "frontend", "react", "react폴더 구성", "팀프로젝트", "프론트엔드"]
author: "프론트 꿈나무"
original_url: "https://developer-smh.tistory.com/16"
---

#### 전 게시물 

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
 

오늘은 여기서 가장 핵심이 되는 폴더를 뽑아서 왜 그렇게 나눴는지 알아보겠습니다.

(순서는 보기 내용을 기준으로 위에서 아래입니다)

 

 

---

### global 폴더

---

 

 

담긴 폴더들

-  common.js : 자주 쓰는 스타일 속성을 export 해주는 파일이다  
  

더보기
이해를 돕기 위한 코드  
  
선언 예시  

```javascript
import { css } from "styled-components";

//상수에 css속성을 담아서 외부에서 쓸 수 있도록 내보내주는 코드들
export const parentSize = css`
    width:100% ;
    height: 100%;
`

export const felxRow = css`
  display: flex;
  flex-direction: row;
`

export const felxColumn  = css`
  display: flex;
  flex-direction: column;
`
```
 

사용 예시

```
S.SubMenu =styled.li`
    width: 150px;
    height: 50px;
    ${felxColumn} /*사용하고 싶은 속성이 담긴 상수를 적으면 됨*/
    &>a{
        display: block;
        line-height: 50px;
        text-align: center;
        font-size: 16px;
        color: #111;
    }

    &> a:hover{
        color: #6E58FF;
        text-decoration: underline;
    }
`
```
  
  

-  global.js : 전역에 필요한 스타일이 담겨이는 파일 예) list-style,color...등등  
  

더보기
이해를 돕기 위한 코드  
  
설명: app.js에 하위 컨포넌트들에게 적용하는 스타일을 정의하는 폴더이다   
  
선언 예시  

```yaml
import { createGlobalStyle } from "styled-components";

const GlobalStyle = createGlobalStyle`

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    text-shadow: 0 0 2px rgba(0, 0, 0, 0.05);
    letter-spacing: -0.4px;
    list-style: none;
    text-decoration: none;
    color: #111;
  }

  body {
    line-height: 1.3;
  }

  button {
    cursor: pointer;
    border: 0px;
  }

  

`

export default GlobalStyle;
```
 

사용예시 (app.js)  
  

```c
import './App.css';
import { RouterProvider } from 'react-router-dom';
import GlobalStyle from './global/global'
import router from './router/router';

function App() {
  return (
 <>
   {/*이렇게 사용하면 모든 컨포넌트에 적용됨*/}
  
 
  );
}

export default App;
```
  
  

- theme.js : 말 그대로 웹사이트를 만들 때 필요한 배경색,폰트크기,등을 객체로 담고 있는 파일이다.  
                선언은 어렵지만 사용을 쉽게 할 수 있다는 장점이 있다.  
  

더보기
이해를 돕기 위한 코드  
  
선언 예시  

```
const theme = {};

theme.PALLETE = {
  primary: {
    main: "#6E58FF",
    sub: "#6DE701",
    default: "#1A1B1E",
  },
  secondary: "#f1ebf5",
  white: "#fff",
  black: "#000",
  gray: {
    100: "#F2F2F2",
    200: "#E6E6E6",
    300: "#D9D9D9",
    400: "#CCCCCC",
    500: "#C0C0C0",
    600: "#B3B3B3",
    700: "#A6A6A6",
    800: "#999999",
    900: "#8D8D8D",
  },
  error: "#eb6144",
  background: {
    white: "#fff",
    purple: "#6E58FF",
  },
};
```
  
사용예시   

```c
/*객체에서 원하는 스타일만 꺼내서 사용할 수 있다.*/
   
   &> a:hover{
        color: ${theme.PALLETE.background.purple.main};
        text-decoration: underline;
    }
```

 

 

 

 

 

---

### moduls폴더

---

담긴 파일들

 

설명 : 모듈에서는 전역에서 사용되는 상태를 관리 할 수 있는 js파일들이  들어있다.

- index.js : 모든 전역상태를 담아서 store를 구성하는 중요한 역할을 한다.
더보기
코드  

```javascript
import { combineReducers } from 'redux';
import auth from './auth';

//상태를 객체(object)형태로 담아서 내보낸다
const rootReducer = combineReducers({
    auth
})

export default rootReducer;
```
  
  
  

- auth.js : 전역상태중 하나로 웹사이트에서  빠질 수 없는 로그인 여부를 담고 있다.
더보기
이해를 돕기 위한 코드  

```javascript
// src/reducers/auth.js

import { createAction, handleActions } from 'redux-actions';

// 로그인 액션 타입
const LOGIN = "auth/LOGIN";
const LOGOUT = "auth/LOGOUT";
//유저정보 액션 타입
const SET_USER = "user/SET_USER"

// 액션 생성자
export const login = createAction(LOGIN);   // payload는 true
export const logout = createAction(LOGOUT); // payload는 false
export const setUser = createAction(SET_USER)

const initialUser = {
  id: "",
  email: ""
};

// 초기 상태
const initialState = {
  isLoggedIn: false,
  current : initialUser
};

// 리듀서
const auth = handleActions(
  {
    [LOGIN]: (state, action) => ({
      ...state,
      isLoggedIn: true,
    }),
    [LOGOUT]: (state, action) => ({
      ...state,
      isLoggedIn: false,
      current : initialUser
    }),
    [SET_USER]: (state, action) => ({
      ...state,
      current : action.payload
    }),
  },
  initialState
);

export default auth;
```
  
  

 

 

  
  

 

 

 

 

---

### router폴더

---

 

담긴 파일들 

 

- router.js :  URL경로에 따라서 호출될 컨포넌트들을 정의해 놓고 있다.
더보기
초기 세팅된 코드  
  
router.js (선언)  

```
import {createBrowserRouter} from 'react-router-dom';
import LayOut from '../pages/Layout/LayOut';
import Home from '../pages/homepage/Home';

const router = createBrowserRouter([
    {
        path :"/",
        element : ,
        children : [
            {
                index : true,
                element : 
            }
        ]
    }
],
{
    future: {
        v7_startTransition: true,
        v7_fetcherPersist : true,
        v7_normalizeFormMethod : true,
        v7_partialHydration : true,
        v7_relativeSplatPath : true,
        v7_skipActionErrorRevalidation : true,
    },
  })

export default router
```
 

app.js(사용)  
  

```
import './App.css';
import { RouterProvider } from 'react-router-dom';
import GlobalStyle from './global/global'
import router from './router/router';

function App() {
  return (
 <>
  
  
 
  );
}

export default App;
```
  
  

 

 

> 블로그를 쓰면서 폴더 초기 세팅까지 하려니   
경험치 2배 이벤트를 하는 느낌입니다.   
힘든만큼 제가 팀프로젝트를 통해서 얻어가는 게  
많다고 느꼈고 끝까지 완성도 높은 프로젝트와 글로  
마무리 해보겠습니다  
  
  
  
  
  

 

### 감사합니다
