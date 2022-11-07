# **시간 복잡도(time complexity)**

## **시간 복잡도(time complexity)**
-   `시간 복잡도`: 입력값(N)에 따른 연산 횟수
    -   프로그램의 성능을 판단하는 지표로 사용
-   표현 방법
    1.  `빅오 표기법(Big-O)` : 가장 최악의 연산 횟수를 고려한 표기 방법
        -   프로그래밍을 할 때에는 최악의 경우도 고려해야 하기 때문에 시간 복잡도에서 주로 사용하는 표현 방법
    2.  빅오메가 표기법(Big-Ω) : 가장 최소의 연산 횟수를 고려한 표기 방법
    3.  빅세타 표기법(Big-θ) : 최소와 최악의 평균적인 연산 횟수를 고려한 표기 방법

## **빅오 표기법(Big-O Complexity)**
- 빅오 표기법
    -   O(1) : 입력값과 상관 없이 연산 횟수가 일정(constant complexity)
    -   O(n) : 입력값에 따라서 연산 횟수가 비례적으로 증가(linear complexity)
    -   O(log n) : BST와 같은 로직의 시간 복잡도(logarithmic complexity)
    -   O(n2) : 입력값의 제곱수로 연산 횟수의 비율이 증가(qudratic complexity)
    -   O(2n) : 2의 배수 형태로 연산 횟수가 증가(exponential complextiy)

<p align="center">
    <img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2FbV1tjt%2FbtrQxbye55F%2Fpbb3MXTmO6PsoEXSkkwWs1%2Fimg.png" alt="시간 복잡도"/>
    <br>출처 : https://www.bigocheatsheet.com/</br>
</p>
