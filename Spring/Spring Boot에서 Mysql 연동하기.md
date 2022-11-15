# **Spring Boot에서 Mysql 연동하기**

## **Spring Boot에서 Mysql 연동하기**
-   application.yml 코드 수정

``` yaml
# localhost:8080 서버 연결
server:
  address: localhost
  port: 8080

spring:
  jpa:
    database-platform: org.hibernate.dialect.MySQL5InnoDBDialect
    open-in-view: false
    hibernate:
      ddl-auto: create-drop # 애플리케이션 시작 시 테이블 재생성
    show-sql: true
    properties:
      hibernate:
        format_sql: true
  # Mysql 사용
  datasource: 
    driver-class-name: com.mysql.cj.jdbc.Driver
    url: jdbc:mysql://localhost:3306/test # test는 Mysql에 있는 DataBase 이름으로 설정
    username: root # username 설정
    password: root # 비밀번호 입력

logging:
  level:
    org:
      hibernate:
        SQL: DEBUG
        type:
          descriptor:
            sql:
              BasicBinder: TRACE
```
