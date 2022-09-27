# 큐(Queue)

## 큐(Queue)
-   **큐(Queue)** : 데이터를 순서대로 쌓아서 사용하는 구조
-   큐의 종류
    -   선형큐(Linear Queue)
    -   원형큐(Circular Queue)
    -   디큐(Dequeue)


## **선형큐(Linear Queue)**
-   구조가 선형인 큐
-   특징
    1.  FIFO(First In Firt Out) 또는 LILO(Last In Last Out)
    2.  입출력 방향 고정
    3.  하나의 데이터만을 입출력 가능
-   구조
    -   front : 처음 요소
    -   rear : 마지막 요소
    -   enqueue : 데이터 넣기
    -   dequeue : 데이터 빼기
-   장치끼리 통신을 할 때 발생하는 속도/시간 차이를 줄이기 위해서 사용(buffer)
-   구현 - Queue 데이터 타입을 LinkedList로 구현

```
Queue<Integer> queue = new LinkedList<>();
```

<p align="center">
  <img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcCkW1T%2FbtrMJP6l2ZH%2FZcPq4TQvFkbRJmanYbQaiK%2Fimg.png" alt="Linear Queue"/>
</p>

## **원형큐(Circular Queue)**
-   구조가 원형인 큐
-   배열로 구현된 선형큐에서 계속해서 데이터를 넣고 뺐을 때 발생하는 문제(배열 포화 상태)를 보안한 큐
-   구조
    -   front : 처음 요소의 앞을 가리킨
    -   rear : 마지막 요소
    -   공백상태 : front == rear
    -   포화상태 : front == (rear + 1) % QUEUE\_SIZE
    -   공백상태와 포화상태 구분을 위해서 공간 하나는 사용하지 않음

<p align="center">
  <img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FOabDT%2FbtrMMaIPQ3b%2F5svV2jhlRf8iCKSIuHX3C0%2Fimg.png" alt="Circular Queue"/>
</p>


## **덱(Dequeue, Double Ended Queue)**
-   양방향에서 입출력이 가능한 큐
-   특징
    1.  stack과 queue 구현해서 사용 가능
    2.  양방향으로 데이터 추가, 삭제

<p align="center">
  <img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbM8KYy%2FbtrMN8QM2Zv%2Flw1z08WBS5xcSEQbcnnx3k%2Fimg.png" alt="Dequeue"/>
</p>
