## HashTable
> 배열과 해시함수를 이용하여 map을 구현한 자료구조
> 상수시간O(1)의 데이터 접근속도를 가진다(최악은 O(N))


<img src="https://github.com/Jung-MinGi/study/assets/118701129/4f9ab8f3-2348-451c-a835-8c493d2263bc" width="300" height="250"/>

* 특정 키를 해싱 후 그 값을 배열의 인덱스로 삼아 데이터를 저장하는 것

## [해시 충돌]
1. 서로 다른 데이터여도 해싱값이 같은 경우
2. 해싱된 값에 모듈러 연산의 결과값이 같은 경우


### 해시 충돌 해결 
1. Separate Chaining
* 배열안을 LinkedList로 만들어 인덱스가 같아도 list에 담으면 
