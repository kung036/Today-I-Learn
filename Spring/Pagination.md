# Pagination

## **Pagination 이란?**

-   데이터의 페이지와 페이지 크기만큼 나누어서 데이터를 요청하는 방식

<p align="center">
    <img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2Fcq8PmT%2FbtrP4xgkvOF%2FHrHE0D3x8tAde539Fps7vK%2Fimg.png"/>
</p>

## **REST API의 Pagination 방법**

### **Offset-Based Paginagtion**
-   offset 쿼리를 이용해서 페이지와 페이지 크기 단위의 데이터 요청/응답하는 방식
-   장점 : 페이지 이동 가능
-   단점
    -   페이지 이동 시 데이터 변경이 발생하면 중복 데이터 생성
    -   RDBMS에서 Offset 쿼리를 사용을 통한 성능 저하

### **Cursor-Based Pagination**
-   cursor 개념을 이용해서 마지막으로 전송된 데이터를 기준으로 필요한 데이터 N개만큼 데이터 요청/응답하는 방식
-   인스타그램의 스크롤 방식
-   장점 : 실시간으로 변하는 리소스를 사용하는 경우 발생하는 중복 전송 방지 

참고 사이트 : [https://wonyong-jang.github.io/database/2020/09/06/DB-Pagination.html](https://wonyong-jang.github.io/database/2020/09/06/DB-Pagination.html)

## **Spring을 이용해서 Offset-Based **Pagination** 구현**

-   Pagination 구현에 사용되는 import 파일

``` Java
import org.springframework.data.domain.Page;
import org.springframework.data.domain.PageRequest;
import org.springframework.data.domain.Pageable;
```

-   변수

``` Java
int page; // 현재 페이지 번호
int size; // 페이지의 크기
```

-   controller(API 계층) 
    -   service로부터 page와 size로 나누어진 데이터를 Page<T> 객체로 받음
    -   Page<T> 객체의 getContent() 메서드를 통해서 List<T> 형태의 객체 반환
    -   이때 T는 Spring MVC의 Entity 클래스

``` Java
// service : 서비스 계층 객체
Page<T> pageData = service.finds(page-1, size); // page-1 이유 : 시작 index가 0이기 때문
List<T> data = pageData.getContent();
```

-   service(비즈니스 계층)
    -   repository의 인자값으로 전달할 Pageable 객체 생성
    -   Pageable 객체의 초기화는 PageRequest.of() 메서드 이용

``` Java
Pageable pageable = PageRequest.of(page, size, Sort.by("정렬기준(Entity의 멤버변수)").descending()); // 정렬기준의 내림차순 정렬
Page<T> pageObject = memberRepository.findAll(pageable); // page와 size로 나누어진 데이터
```

-   repository
    -   CrudRepository를 상속받은 인터페이스 repository에 모든 데이터를 page와 size에 따라 필요한 데이터를 가져올 수 있게 하는 메서드 findAll() 추가하기

``` Java
Page<T> findAll(Pageable pageable)
```