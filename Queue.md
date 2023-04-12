# codingTestBClass
정리는 정의, 장단점, 예상면접질문

## 큐란?
- 차례를 기다리는 사람이나 승용차의 열 이라는 의미
- 가장 먼저 들어온 데이터가 가장 먼저 나가게 되는 구조이다.
- FIFO(First In First Out, 선입선출) 구조라고도 한다.

![image](https://user-images.githubusercontent.com/103026978/231397695-7e65c1e1-9356-4734-b743-4b1da5c8668f.png)
데이터를 넣는 것은 Enqueue, 반대로 데이터를 꺼내는 것을 Dequeue 라고 하며, 새로운 데이터가 들어가는 위치는 가장 뒤인 Back에 들어가게 되고, 데이터 나가는 위치는 가장 앞인 Front에서 꺼낸다.

### 큐 연산
- enqueue: 큐에 데이터를 저장함
- dequeue: 큐의 가장 앞 데이터를 꺼냄(삭제)
- peek: 큐의 가장 앞 데이터를 꺼내되(반환), 삭제하지 않음
- isEmpty: 큐가 빈 경우 TRUE(1)을, 그렇지 않은 경우 FLASE(0)을 반환함

### 큐의 종류
- 선형 큐
  - 크기가 제한되어 있음
  - 빈 공간을 사용하려면 모든 자료를 꺼내거나, 데이터를 한 칸 씩 옮겨야함
  - 마지막 배열에 도달 했을 때, 실제로는 데이토 공간이 남아있지만 오버플로우가 발생함
- 원형 큐
  - 선형 큐의 문제점을 보완함
  - front가 큐의 끝에 닿으면 큐의 맨 앞으로 자료를 보내어 원형으로 연결하는 방식임
- 링크드 큐