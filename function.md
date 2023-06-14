<details>
<summary>replace</summary>
<div markdown="1">
  
  ### 특정 문자 제거하기
  
  ```str.replace('AB', '');```

  str 문자열에서 'AB' 부분을 찾아서 ''로 반환하는 형식.

  전체 문자열에서 첫 번째로 찾은 문자열만 바꿔준다.
  
  ### 특정 문자 모두 제거하기
  
  ```str.replace(/AB/g, '');```
  
  '/'는 정규식의 시작과 끝을 나타낸다.
  
  'g'는 Global Search를 의미하는 플래그로, 전역 탐색을 한다.
  
  ### 특정 문자 대소문자 구분없이 모두 제거하기
  
  ```str.replace(/AB/ig, '');```
  
  'i'는 ignore case를 의미하며, 대소문자를 구분하지 않는다.
  
</div>
</details>
