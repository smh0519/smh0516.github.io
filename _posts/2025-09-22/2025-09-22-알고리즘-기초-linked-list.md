---
title: "알고리즘 기초 - Linked List"
layout: post
date: 2025-09-22 15:17:25 +0900
categories: ["알고리즘", "Linked List", "링크드 리스트", "알고리즘 기초"]
tags: ["알고리즘", "Linked List", "링크드 리스트", "알고리즘 기초"]
author: "프론트 꿈나무"
original_url: "https://developer-smh.tistory.com/31"
---

---

## Linked List란?

---

 

데이터와 그 다음 데이터의 위치를 연결해서 만든 자료구조예요.  
쉽게 말하면 데이터들이 화살표로 연결된 체인 형태라고 생각하면 됩니다.

- 배열(Array)과 달리 연속된 메모리 공간이 필요 없어요.

- 대신 각 데이터는 다음 데이터의 주소(포인터)를 가지고 있어서 서로 연결돼 있습니다.

 

기본 구조

Linked List의 노드(Node) 구조는 일반적으로 이렇게 생겼어요

```python
[데이터 | 다음 노드 주소] -> [데이터 | 다음 노드 주소] -> ... -> None
```

- 데이터: 실제 저장하고 싶은 값

- 다음 노드 주소(next): 다음 노드가 어디 있는지 가리키는 포인터

- 마지막 노드는 None을 가리켜서 끝임을 표시

 

---

## List 종류

---

 

#### - Singly Linked List (단일 연결 리스트)

 

- 노드가 다음 노드만 가리킴

- 탐색은 앞으로만 가능

```bash
10 -> 20 -> 30 -> None
```

#### - Doubly Linked List (이중 연결 리스트)

 

- 노드가 이전 노드와 다음 노드 둘 다 가리킴

- 탐색이 양방향 가능

```bash
None  20  30 -> None
```

#### - Circular Linked List (원형 연결 리스트)

 

- 마지막 노드가 처음 노드를 가리킴

- 리스트를 순환하면서 반복 가능

 

```bash
10 -> 20 -> 30 -> 10 ->
```

---

## 장점과 단점

---

 

<table style="border-collapse: collapse; width: 100%; height: 108px;" border="1" data-ke-align="alignLeft" data-ke-style="style4">
<tbody>
<tr style="height: 17px;">
<td style="height: 17px; text-align: center;"><b>장점</b></td>
<td style="height: 17px; text-align: center;"><b>단점</b></td>
</tr>
<tr style="height: 19px;">
<td style="height: 19px;">- 삽입/삭제가 배열보다 빠름(O(1), 위치만 알면)</td>
<td style="height: 19px;">- 탐색이 느림(O(n)), 순차적으로 찾아야 함</td>
</tr>
<tr style="height: 19px;">
<td style="height: 19px;">- 크기 변경이 자유로움</td>
<td style="height: 19px;">- 포인터 때문에 메모리 사용이 배열보다 많음</td>
</tr>
<tr style="height: 19px;">
<td style="height: 19px;">- 배열처럼 크기 미리 지정 필요 없음</td>
<td style="height: 19px;">- 구현이 조금 복잡함</td>
</tr>
</tbody>
</table>
 

 

 

---

 

## 마무리

---
