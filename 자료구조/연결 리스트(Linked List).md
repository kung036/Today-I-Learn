# 연결 리스트(Linked List)

## **연결 리스트(Linked List)**

-   **연결 리스트** : 값와 다음 노드의 주소를 가진 하나의 노드들이 선형적으로 이어진 자료구조
-   구조 : 노드들이 흩어진 공간에 위치함
-   head node : 연결 리스트의 첫번째 노드
## 특징
1.  쉽고 빠른 노드의 추가 및 삭제 : 시간 복잡도 : O(1)
2.  특정 노드의 값을 찾기 위해서 최대 전체 순회 필요 : 시간 복잡도 : O(N)
## 사용하는 경우
1.  삽입 및 삭제가 빈번히 일어나는 경우
2.  동적 기억장소 관리(dynamic storage managemnet) : 필요한 메모리만 할당
3.  걸비지 컬렉션(Garbage Collection)

## 구현 - Stack 데이터 타입 이용
``` Java
LinkedList<String> linkedList = new LinkedList<>();
```

<p align="center">
    <img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbYUD8v%2FbtrNzFuy9OH%2FT139kJs9CmtivbIpr2GJD0%2Fimg.png" alt="Linked List"/>
</p>