# **영속성 전이(Cascade)**

-   **영속성 전이** : Entity의 상태 변화가 발생하면 연관된 Entity의 상태 변화를 발생시키는 것
-   영속성 전이 방법 : @OneToMany의 property인 cascade 이용
    -   **cascade**의 값
        -   CascadeType.ALL : 연관된 엔티티까지 모든 상태 변화 전이
        -   CascadeType.PERSIST : 연관된 엔티티까지 영속성 전이
        -   CascadeType.REMOVE : 연관된 엔티티까지 엔티티 제거
        -   CascadeType.REFRESH : 연관된 엔티티까지 데이터베이스로부터 객체값을 다시 가져오기(새로고침)
        -   CascadeType.DETACH : 연관된 엔티티까지 영속성 컨텍스트에서 엔티티 제거

```Java
// 예제
@OneToMany(mappedBy = "member", cascade = CasCadeType.ALL)
private Order order;
```