# 해시 테이블(Hash Table)

## **해시 테이블(Hash Table)**

-   **해시 테이블** : 해시함수으로 생성된 해시를 키와 데이터를 저장하는 위치로 사용한 자료구조
-   인자가 키(key)인 해시함수(Hash function)는 해시(hash)를 생성하고, 해시는 메모리 위치를 가리키고 이 메모리 위치에 데이터(value)를 저장
<br></br>
- 구조
    -   키(key) : 해시함수의 인력값으로, 중복허용 X
    -   해시함수(hash function) : 키를 해시로 변경하는 함수, 해시 충돌을 최대한 줄이는 것을 목표로 함
    -   해시(hash) : 키를 햄시함수에 넣어서 생성된 값, 데이터 저장되는 메모리 인덱스
    -   데이터(value) : 메모리에 저장되는 값으로, 중복허용 O
    -   해시 출돌(Hash collision) : 서로 다른 키가 같은 해시를 가지는 경우
<br></br>
-   특징
    1.  빠른 저장, 삭제, 검색 : 시간복잡도 O(1), 해시 충돌 시 시간복잡도 O(N)
    2.  해시 충돌 발생 가능
    3.  낮은 공간 효율성 : 데이터 저장 전 메모리 공간을 미리 생성
    4.  해시함수에 대한 높은 의존도 : 해시함수 복잡도 ↑ ∝ 데이터 삭제, 저장, 검색의 시간 복잡도 ↑ 
<br></br>
-   해시 알고리즘
    -   Division Method : 키(숫자)를 메모리 크기로 나눈 나머지가 해시 값으로 사용하는 알고리즘
    -   Digit Folding : 키(문자열)를 ASCII 코드로 변경 후 값들의 합을 해시 값으로 사용하는 알고리즘
    -   Multiplication Method : (kn mod 1) \* a의 값을 해시 값으로 사용하는 알고리즘(k는 키(숫자), n은 0과 1 사이의 실수, a는 2의 제곱수)
    -   Universal Hashing : 여러 해시 함수 중 무작위로 해시함수 사용
<br></br>
-   해시 충돌 해결 방법
    1.  개방 연결법(open addressing) : 해시 충돌이 발생하면 다른 메모리 위치에 데이터를 저장하는 방식
        1.  Linear Probing : 고정된 숫자만큼 메모리 위치 변경
        2.  Quadratic Probing : 충돌이 발생한 횟수만큼 제곱해서 메모리 위치 변경
        3.  Double Hasing Probing : 다른 해시함수를 이용해서 새로운 메모리 위치 생성
    2.  분리 연결법(Seperate Chaining)
        -   해시충돌이 발생하면 다양한 자료구조를 이용해서 데이터 주소를 저장하는 방식
        -   동일한 메모리 주소에 저장되는 값들이 많아지면 검색의 시간복잡도 ↑
    3.  저장소 확장(Resize)
        -   메모리의 공간을 두 배로 늘려서 해시충돌 발생 가능성 ↓

<p align="center">
    <img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbeNT0T%2FbtrNzEbq121%2F02bWirEWQ2JOnKclRU2oO1%2Fimg.png" alt="Hash Table"/>
</p>