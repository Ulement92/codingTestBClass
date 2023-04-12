# codingTestBClass
정리는 정의, 장단점, 예상면접질문

## 스택이란?
- 단어 자체의 의미는 '차곡 차곡 쌓여진 더미'를 의미
- 개념: 메모리의 스택 영역은 함수의 관계되는 지역변수, 매개변수, 리턴 값등의 임시데이터를 저장한다.
- LIFO(Last In First Out, 후입선출) 구조라고도 한다.

### 스택의 구조
가장 먼저 저장되는 데이터는 스택의 아래쪽부터 쌓이고, 다음 저장되는 데이터가 바로 그 위에 쌓인다.![img1 daumcdn](https://user-images.githubusercontent.com/103026978/230016861-4825e4aa-ea0a-4b59-9a53-1f30428effff.png)
![img1 daumcdn](https://user-images.githubusercontent.com/103026978/230016899-799be533-a030-47df-a5b5-d6a6b45046ba.png)
스택에 새로운 데이터를 추가하는 것을 PUSH라고 한다.
PUSH를 하면 기존 데이터 위에 새 데이터가 순서대로 쌓아진다.

![img1 daumcdn](https://user-images.githubusercontent.com/103026978/230017050-bddc4af5-3d86-4494-b4f5-9b0b19a95d56.png)
스택에 있던 데이터를 다시 빼내는 것을 POP이라고 한다.

이처럼 스택은 기본적으로 PUSH와 POP을 통해 데이터의 추가/제거가 가능하며, 이 PUSH/POP 되는 데이터의 크기는 프로그래머가 정할 수 있다.

스택이 밑에서부터 데이터를 추가하는 이유는 커널영역을 침범하지않기 위해서 밑에서부터 데이터를 추가한다.
> 커널 영역이란?
> 

### 스택의 TOP & BOTTOM
- TOP/BOTTOM은 스택의 특정 위치를 가리킨다.
- TOP은 가장 최근에 스택에 저장된 값, BOTTOM은 가장 처음 스택에 저장된 값을 가리킨다.

![img1 daumcdn](https://user-images.githubusercontent.com/103026978/230017968-092ddbb5-3ad6-4913-bc4f-8b7528dbfcf4.png)
![img1 daumcdn](https://user-images.githubusercontent.com/103026978/230018076-aa9a31fc-5aca-4df7-a7a9-52f9a9cba1a0.png)

만약 C라는 데이터가 PUSH가 되면

![img1 daumcdn](https://user-images.githubusercontent.com/103026978/230018168-6c6222ae-cf6e-46eb-bb9e-65b4bd3290f6.png)

TOP은 C를 가리키며, BOTTOM은 그대로다.

BOTTOM의 위치는 항상 스택 가장 아랫값을 가리키고 있기 때문에 고정된다. 하지만 TOP의 위치는 데이터가 추가되거나, 데이터가 제거될 때 마다 달라진다.

### 스택의 장단점?
장점
- 구조가 단순해서, 구현이 쉽다.
- 데이터 저장/읽기 속도가 빠르다.

단점
- 데이터 최대 갯수를 미리 정해야 한다.
- 저장 공간의 낭비가 심할 수 있다.
