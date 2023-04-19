# codingTestBClass
정리는 정의, 장단점, 예상면접질문
## 우선순위 큐란?
- 선입선출 방식이 아닌 우선순위를 기준으로 삭제
- 우선순위가 같다면 큐에 삽입된 시점을 기준으로 삭제
- 배열, 연결리스트, 힙 기반으로 우선순위 큐 구현할 수 있고, 각각 시간복잡도가 다름
- 배열과 연결리스트의 경우, 모든 인덱스를 탐색해야해서 최악의 경우 성능이 별로일 수 있음
  - But, 구현이 간단!
#### 배열 기반 우선순위 큐
- 삽입: O(n)
- 삭제: O(1)
#### 연결리스트 기반 우선순위 큐
- 삽입: O(n)
- 삭제: O(1)
#### 힙 기반 우선순위 큐
- 삽입: O(logN)
- 삭제: O(logN)
### 클래스 정의
```js
class QElement {
  constructor(element, priority) {
    this.element = element;
    this.priority = priority;
  }
}

// 우선순위 큐
class PriorityQueue {
  constructor() {
    this.queue = [];
  }
}
```
### 삽입 메소드 구현
```js
// 데이터의 우선순위에 따라 큐의 적절한 위치에 삽입
enqueue(element, priority) {
  // QElement 객체 생성
  const qElement = new QElement(element, priority);
  let isContain = false;
  
  // 전체 데이터를 순회하면서 자신의 우선순위가 더 높은 위치를  탐색
  // splice 함수는 배열의 기존 요소를 삭제 또는 교체하거나 새 요소를 추가하여 배열의 내용을 변경
  // array.splice(startIndex, deleteCount, item1, item2, ...)
  for(let i=0, j=this.queue.length; i<j; i++) {
    if(this.queue[i].priority < element.priority) {
      this.queue.splice(i, 0, qElement);
      isContain = true;
      break;
    }
  }
  
  // 큐에 자신보다 더 낮은 우선순위를 가진 요소가 없을 때, 큐의 맨 마지막에 삽입
  if(!isContain) {
    this.queue.push(qElement);
  }
}
```
### 삭제 메소드 구현
```js
dequeue() {
  // 큐가 비어있을 때는 오류를 발생시킨다.
  // 비어있지 않다면 첫번째 요소를 삭제하고 반환한다.
  if(this.queue.length === 0) {
    return new Error("우선순위 큐에 데이터가 없습니다.");
  }
  return this.queue.shift();
}
```
### 유틸리티 메소드 구현
```js
front() {
  // 큐가 비어있을 때는 오류를 발생시킨다.
  // 비어있지 않다면 첫번째 요소를 반환한다.
  if(this.queue.length === 0) {
    return new Error("우선순위 큐에 데이터가 없습니다.");
  }
  return this.queue[0];
}

rear() {
  // 큐가 비어있을 때는 오류를 발생시킨다.
  // 비어있지 않다면 마지막 요소를 반환한다.
  if(this.queue.length === 0) {
    return new Error("우선순위 큐에 데이터가 없습니다.");
  }
  return this.queue[this.queue.length-1];
}

isEmpty() {
  // 큐의 길이를 0과 비교하여 큐가 비어있는지 반환한다.
  return this.queue.length === 0;
}

print() {
  // ES6 Array.forEach 메소드로 큐를 순회하면서 문자열을 만들어낸다.
  let str = "";
  this.queue.forEach(item => str += item.element + " ");
  return str;
}
```
