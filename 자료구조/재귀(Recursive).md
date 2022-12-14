# 재귀

## **재귀함수**

-   **`재귀(recursive)`**</span> : 문제를 작은 문제로 나누고 이 작은 문제를 해결을 통해서 문제를 해결하는 방식
-   **`재귀함수`**</span> : 자기 자신을 호출하는 메서드
    -   장점
        -   코드 간결 및 수정 용이
        -   변수 사용 횟수 감소
    -   단점
        -   직관적인 코드 흐름 파악이 어려움
        -   proccess stack에 지역변수, 매개변수, 반환값 저장 → 많은 메모리 사용
        -   복귀할 때 컨텍스트 스위치 비용 발생
    -   사용하는 경우
        -   작은 문제로 나눌 수 있는 경우
        -   중첩된 반복문이 많거나 중첩 횟수 예측이 어려운 경우
        -   변경 가능 상태(mutable state)를 제거해서 오류 발생 가능성을 줄이는 경우
    -   <U>모든 재귀 함수 → 반복문 표현 가능</U>

## **재귀함수 작성**

1.  재귀함수의 입출력 정의
    -   재귀함수 : 입력 → 출력
2.  기준 설정 및 문제 분해하기
    -   기준 : 입력값이나 문제의 순서와 크기
    -   문제 분해하기
        -   더 이상 분해 가능한 경우와 아닌 경우
3.  재귀의 기초(Base Case)
    -   종료 조건 구현(더 이상 분해되지 않는 경우)
4.  나머지 경우의 수(Recursive Case)
    -   재귀의 기초 이외의 경우의 수 구현
5.  코드 구현