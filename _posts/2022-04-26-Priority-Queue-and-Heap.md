---
layout: post
title: Priority Queue and Heap
category: DS-and-Algorithm
---

### Table of contents
- [우선순위 큐](#우선순위-큐priority-queue)
	- [Enqueue](#enqueue)
	- [Dequeue](#dequeue)
	- [구현](#구현)
- [힙](#힙heap)
	- [삽입 연산](#삽입-연산)
	- [최소값 삭제](#최소값-삭제)
		- [삭제 후 뒤처리 과정](#삭제-후-뒤처리-과정)
	- [구현](#구현)
		- [완전 이진 트리를 배열로 나타내는 방법](#완전-이진-트리를-배열로-나타내는-방법)
		- [특징](#특징)

---

# 우선순위 큐(Priority Queue)
새 요소에 우선순위를 부여해서 큐에 삽입하고 가장 높은 우선순위를 갖는 요소부터 빠져나오도록 한다.

## Enqueue

우선순위 큐는 요소의 우선순위 오름차순으로 연결된다.

[Front] 2 → 17 → 22 → 56 → 117 [Rear]

여기에 우선순위 20의 요소를 삽입하면

[Front] 2 → 17 → 20 → 22 → 56 → 117 [Rear]

## Dequeue
전단만 제거해서 반환하면 끝

## 구현
우선순위 큐는 그저 우선순위 순서로 요소가 제거되도록 하는 큐이다.

새 요소를 삽입할 때 삽입할 위치를 찾기 위해서는 순차 탐색을 해야하는데, 정말 이 방법밖에 없는 걸까?

효율적인 우선순위 큐의 구현을 위해 **힙**이라는 자료구조를 사용할 수 있다.

---

# 힙(Heap)
힙이란 **힙 순서 속성(Heap Order Property)**을 만족하는 **완전 이진 트리**이다.

- 완전 이진 트리: 최고 깊이를 제외한 모든 깊이의 노드들이 완전히 채워져 있는 이진 트리
- 힙 순서 속성: 트리 내의 모든 노드가 부모 노드보다 커야 함

> 힙에서 가장 작은 데이터를 갖는 노드는 루트 노드이다.
> 

힙은 딱 두 가지 연산만 가지고 있다. (더 추가한다면 말릴 수는 없지만...)

1. 새 노드를 삽입
2. 루트 노드를 없애는 ‘최소값 삭제' 연산

## 삽입 연산

힙의 삽입 연산은 다음 세 단계를 거쳐 수행된다.

1. 힙의 최고 깊이, 최 우측에 새 노드를 추가한다. (이때 힙은 완전 이진 트리를 유지하도록 해야 함)
2. 삽입한 노드를 부모 노드와 비교한다.
    1. 삽입한 노드가 부모 노드보다 크면 제 위치에 삽입된 것이므로 연산 종료
    2. 부모 노드보다 작으면 다음 단계 진행
3. 삽입한 노드가 부모 노드보다 작으면 부모 노드와 삽입한 노드의 위치를 서로 바꾼다. 바꾸고 나면 2단계를 다시 진행(루트와 비교할 때까지)

## 최소값 삭제

힙의 최소값을 삭제한다는 것은 곧 루트 노드를 삭제한다는 말과 같다.

삭제하는 것은 별 문제가 아니다.

삭제한 후에 힙의 ‘힙 순서 속성'을 유지하기 위해 해야 하는 일이 문제다.

### 삭제 후 뒤처리 과정

1. 힙의 최고 깊이, 최 우측에 있던 노드를 루트 노드로 옮겨온다.
2. 옮겨온 노드의 양쪽 자식을 비교하여 작은 쪽 자식과 위치 교환
3. 옮겨온 노드가 더 이상 자식이 없는 잎 노드가 되거나 양쪽 자식보다 작은 값을 갖는 경우 연산 종료, 그렇지 않으면 단계 2 반복

## 구현

이진 트리를 구현한 것처럼 링크드 리스트 기반으로 할 수도 있지만, 그러면 힙의 가장 마지막 노드, 즉 최고 깊이의 최 우측 노드를 찾는 데에 문제가 있다.

따라서 힙 구현의 자료구조로는 배열이 더 인기 있다.

힙은 완전 이진 트리이다. 완전 이진 트리는 배열로 구현하기에 아주 좋은 자료구조이다.

### 완전 이진 트리를 배열로 나타내는 방법

- 깊이 0의 노드는 배열의 0번 요소에 저장
- 깊이 1의 노드(2개)는 배열의 1~2번 요소에 저장
- 깊이 2의 노드(4개)는 배열의 3~6번 요소에 저장
- 깊이 n의 노드(2^n개)는 배열의 2^n-1 ~ 2^(n+1)-2번 요소에 저장

### 특징

- k번 인덱스에 위치한 노드의 양쪽 자식 노드들의 인덱스
    - 왼쪽 자식 노드: 2k + 1
    - 오른쪽 자식 노드: 2k + 2
- k번 인덱스에 위치한 노드의 부모 노드 인덱스: (k-1) / 2