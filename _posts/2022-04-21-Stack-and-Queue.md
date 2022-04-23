---
layout: post
title: Stack and Queue
category: DS-and-Algorithm
---

### Table of contents
- [Stack](#stack)
	- [개요](#개요)
	- [주요 기능](#주요-기능)
		- [Push](#Push)
		- [Pop](#Pop)
	- [구현](#구현)
		- [배열 이용](#배열-이용)
		- [연결 리스트 이용](#연결-리스트-이용)
- [Queue](#queue)
	- [개요](#개요)
	- [순환 큐](#순환-큐)
		- [Empty? Full?](#empty-full)
	- [링크드 큐](#링크드-큐)

---

# [Stack](#stack)

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

# [Queue](#queue)
## [개요](#개요)

FIFO(First In, First Out) 구조

큐의 가장 앞 요소를 전단(Front), 마지막 요소를 후단(Rear)이라고 부름

Front에서 Dequeue, Rear에서 Enqueue가 이루어짐

![IMG_51C1E02E6EFE-1](https://user-images.githubusercontent.com/94118504/164888164-2bee3a3c-8d64-4e80-9794-2ed96f899eb3.jpeg)

## [순환 큐](#순환-큐)
배열로 큐를 구현한다고 생각해보자.

Dequeue를 수행하고 나면 모든 요소를 한 칸씩 옮겨야 한다.

![IMG_FCD6740E7ACA-1](https://user-images.githubusercontent.com/94118504/164888204-6df59049-d9c4-4a8c-be9c-e8a6d3bac105.jpeg)

이 문제를 해결하기 위해 Front를 가리키는 변수를 도입할 수 있다.
하지만 새로운 문제가 발생한다.
용량이 6이라고 치면, 제거 연산을 3번 할 경우 사용 가능한 용량은 반만 남게 된다.

![IMG_E8E7F18FF669-1](https://user-images.githubusercontent.com/94118504/164888242-9039043d-e3d1-4abc-826f-56b332a6c8bf.jpeg)

=> Front와 Rear를 연결시키면 해결

![IMG_42524CB53BC2-1](https://user-images.githubusercontent.com/94118504/164888257-17edfdbf-4a8e-449c-a703-2dc0857ff547.jpeg)

### [Empty? Full?](#empty-full)
위의 예에서 Enqueue를 한번 더 실행하게 되면 가득 찬 상태가 된다.

Front == Rear 인 경우, 순환 큐가 비어있는 상태인지 가득 찬 상태인지 어떻게 알까?

일반적인 방법은 큐를 생성할 때 실제 용량 + 1로 만들어서 Front와 Rear 사이를 비우는 것이다.

이러면 큐가 비어 있을 때는 Front == Rear, 차 있을 때는 Rear가 Front보다 1 작은 값이 된다.

![IMG_E9DE814A3BC6-1](https://user-images.githubusercontent.com/94118504/164888299-74778909-431e-419f-b26d-a66128092dd2.jpeg)

## [링크드 큐](#링크드-큐)
Front, Rear, 노드 수를 나타내는 변수로 queue 구조체 선언

각 노드는 데이터와 다음 노드 포인터로 구성