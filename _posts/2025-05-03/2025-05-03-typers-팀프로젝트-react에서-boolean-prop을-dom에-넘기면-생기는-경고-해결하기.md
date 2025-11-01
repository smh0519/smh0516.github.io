---
title: "[Typers 팀프로젝트] -React에서 boolean prop을 DOM에 넘기면 생기는 경고 해결하기"
layout: post
date: 2025-05-03 12:00:18 +0900
categories: ["팀프로젝트/에러", "error", "react", "styled-components", "transient props", "에러 수정"]
tags: ["팀프로젝트/에러", "error", "react", "styled-components", "transient props", "에러 수정"]
author: "프론트 꿈나무"
original_url: "https://developer-smh.tistory.com/18"
---

메뉴를 잘 만들었다고 생각했는데.. 결국 에러가 발견되었습니다.

다행이 코드적인 오류라 금방 고쳤지만 다시는 이런 실수를 하지 않기 위해  
기록하기 위해 이 글을 작성하게 되었습니다.

![image](/assets/img/2025-05-03/img.png)

 

 

 

## ⚠️ 왜 발생하는가?

React는 HTML DOM에 기본 속성 외의 값을 전달하려 할 때 문자열로 변환된 값만 허용합니다. 

```bash
const [ishover,setIsHover] = useState(false)

    const EnterMenu = () =>{
      setIsHover(true)
    }
  
    const LeaveMenu = () =>{
      setIsHover(false)
    }

 
 
  //true or false가 style.js로 props를 넘겨줌
```
 

하지만 위에 코드는 기본 속성이 아닌 값(boolean타입)을 문자열이 아닌 값으로 넘겨주려고 했기 때문에 일어나는 오류 입니다. 

 

 

 

## ✅ 해결 방법

코드에서 발생하는 오류는 원인도 다양하고, 그만큼 해결 방법도 여러 가지가 있습니다. 저는 그중에서도 기존 코드를 최소한으로 수정해 문제를 해결하고자 했고, 이를 위해 transient props(스타일 전용 props) 를 사용하는 방법을 선택했습니다.

 

이 방법은 속성이름 앞에 $를 붙이면 끝나기 때문에 쉽고 간단하게 오류를 해결 할 수 있어서 사용하게 되었습니다.

 

해결된 코드

```bash
 // boolean 값을 props 받는 컨포넌트

스타일
S.SubMenuBox = styled.div`
    padding-bottom:10px ;
    position: absolute;
    top: 101%;
    left: 0;
    width: 100%;
    background-color: #fff;
    border-radius: 0 0 20px 20px;
    overflow: hidden;
    max-height: ${({ $ishover }) => ($ishover ? '300px' : '0')};
    opacity: ${({ $ishover }) => ($ishover ? '1' : '0')};
    transform: translateY(0);
    transition: max-height 0.4s ease, opacity 0.4s ease;
    border-top: 2px solid transparent;
```
 

 

##   왜 $( prefix )로 해결되는가?

styled-components는 $로 시작하는 prop을 보면 "이건 스타일을 위한 prop이구나" 라고 인식해서 DOM에 값을 전달하지 않고,대신 내부 스타일 계산에는 사용됩니다.

 

 

>   
결론 : 내부 스타일에 값을 넘겨 줄 때는   
DOM에 직접 전달되지 않도록 주의하자~!
