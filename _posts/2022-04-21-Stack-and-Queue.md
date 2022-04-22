---
layout: post
title: Stack and Queue
category: DS-and-Algorithm
---

### Table of contents
- [스택](#스택)
	- [개요](#개요)
	- [주요 기능](#주요-기능)
		- [Push](#Push)
		- [Pop](#Pop)
	- [구현](#구현)
		- [배열 이용](#배열-이용)
		- [연결 리스트 이용](#연결-리스트-이용)

---

# [스택](#스택)

## [개요](#개요)
FILO(First In, Last Out) or LIFO(Last In, First Out) 구조

구조의 한쪽 끝에서만 요소의 삽입, 삭제가 이루어진다.

ex)
- 대부분의 네트워크 프로토콜
- 자동 메모리
- 테스트 분석 프로그램

## [주요 기능](#주요-기능)
### [Push](#Push)
스택 위에 새로운 노드를 추가한다.

![IMG_AFDBAF73E3C3-1](https://user-images.githubusercontent.com/94118504/164748041-4b6b6804-aeee-41ed-9b70-876b73c34b6d.jpeg)

### [Pop](#Pop)
스택의 최상위 노드를 제거한다.

![IMG_EB4D77784921-1](https://user-images.githubusercontent.com/94118504/164748092-d61da42f-483a-4893-8f8c-65130d7a7eac.jpeg)

## [구현](#구현)
### [배열 이용](#배열-이용)
- 스택 생성 초기에 사용자가 부여한 용량 만큼의 노드를 한꺼번에 생성
- 장점: 구현 간단
- 단점: 스택 용량을 동적으로 조절하기 어려움

### [연결 리스트 이용](#연결-리스트-이용)
- 장점: 용량 제한 없음
- 단점: 배열처럼 인덱스로 노드에 접근 불가능

---

