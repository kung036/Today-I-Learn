# **인증서를 통한 HTTPS 서버 구현**

## **1. 사설 인증서 생성 - PKCS12**

###   자바에서 지원하는 인증서 형식
-   PKCS12(Public Key Cryptographic Standars #12)
    -   여러 인증서와 키를 가질 수 있음
    -   암호로 보호하는 형식 사용
    -   많이 사용하는 방식
-   JKS(Java Key Store)
    -   PKCS12와 유사
    -   독점 형식
    -   Java 환경에서만 사용 가능
###   mkcert 프로그램 설치
-   mkcert 프로그램을 통해서 local 환경에서 신뢰 가능한 인증서 생성
-   mkcert는 PKCS12형식만 가능
-   mkcert 사이트 : [https://github.com/FiloSottile/mkcert](https://github.com/FiloSottile/mkcert)
-   ubuntu 터미널 또는 WSL 이용해서 mkcert 프로그램 설치

```
$ sudo apt install libnss3-tools
$ wget -O mkcert https://github.com/FiloSottile/mkcert/releases/download/v1.4.3/mkcert-v1.4.3-linux-amd64
$ chmod +x mkcert
$ sudo cp mkcert /usr/local/bin/
```

###   인증서 생성
- 로컬에 인증된 발급기관 추가 → CA 생성 및 설치로 인해서 PKCS12 형식 인증서 생성 가능  
  $ mkcert -install
- PKCS12 형식 인증서 생성 → localhost.p12 인증서 파일 생성  
  $ mkcert -pkcs12 localhost

## **2. 기본 웹 서버 프로젝트 생성**

-   [https://start.spring.io/](https://start.spring.io/) 에서 기본 웹 서버 프로젝트 생성하기(옵션으로 Lombok과 Spring Web 추가하기)

## **3. 사설 인증서를 이용해서 HTTPS 서버 구현**

-   생성한 localhost.p12 인증서를 /root/src/main/resources에 추가하기  
    인증서를 가져오는 방법은 아래의 "발생한 문제 및 해결방법"에서 확인하기

<p align="center">
    <img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcWAvyi%2FbtrREXerYMC%2F3N9V9iGEJmoE4KRJxfZaYk%2Fimg.png" alt=""/>
</p>

-   application.properties에 인증서 관련 설정 추가

```bash
server.ssl.key-store=src/main/resources/localhost.p12	# 인증서가 있는 경로
server.ssl.key-store-type=PKCS12                        # 인증서 형식
server.ssl.key-store-password=changeit                  # 인증서 비밀번호(기본값)
```

-   서버 실행 - 8080 (https)

```
"C:\Program Files\Zulu\zulu-11\bin\java.exe" -XX:TieredStopAtLevel=1 -noverify -Dspring.output.ansi.enabled=always -Dcom.sun.management.jmxremote -Dspring.jmx.enabled=true -Dspring.liveBeansView.mbeanDomain -Dspring.application.admin.enabled=true "-javaagent:C:\Program Files\JetBrains\IntelliJ IDEA 2022.2.3\lib\idea_rt.jar=54956:C:\Program Files\JetBrains\IntelliJ IDEA 2022.2.3\bin" -Dfile.encoding=UTF-8 -classpath C:\Users\sinar\Desktop\BootCamp\Spring\httpstestproject\build\classes\java\main;C:\Users\sinar\Desktop\BootCamp\Spring\httpstestproject\build\resources\main;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.projectlombok\lombok\1.18.24\13a394eed5c4f9efb2a6d956e2086f1d81e857d9\lombok-1.18.24.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.springframework.boot\spring-boot-starter-web\2.7.5\bb4099d0466a62c3b11ab9323babca13bb430a2e\spring-boot-starter-web-2.7.5.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.springframework.boot\spring-boot-starter-json\2.7.5\9c7df04ff37b2e7471632ddeb4a296c5fb6bddee\spring-boot-starter-json-2.7.5.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.springframework.boot\spring-boot-starter\2.7.5\c28e1546461803490588085345ba5d2897d232bc\spring-boot-starter-2.7.5.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.springframework.boot\spring-boot-starter-tomcat\2.7.5\eb7849c52953de44d9712adf45398ccb1a7d4295\spring-boot-starter-tomcat-2.7.5.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.springframework\spring-webmvc\5.3.23\b163527c275b0374371890c0b76c2a2a09f9804b\spring-webmvc-5.3.23.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.springframework\spring-web\5.3.23\193f5276092d9cbe3222c63885b47ca7b2cce97\spring-web-5.3.23.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\com.fasterxml.jackson.datatype\jackson-datatype-jsr310\2.13.4\e6d820112871f33cd94a1dcc54eef58874753b5\jackson-datatype-jsr310-2.13.4.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\com.fasterxml.jackson.module\jackson-module-parameter-names\2.13.4\858ccf6624b5fac6044813e845063edb6a62cf37\jackson-module-parameter-names-2.13.4.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\com.fasterxml.jackson.datatype\jackson-datatype-jdk8\2.13.4\557dbba5d8dfc7b7f944c58fe084109afcb5670b\jackson-datatype-jdk8-2.13.4.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\com.fasterxml.jackson.core\jackson-databind\2.13.4.2\325c06bdfeb628cfb80ebaaf1a26cc1eb558a585\jackson-databind-2.13.4.2.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.springframework.boot\spring-boot-autoconfigure\2.7.5\96646e63a2296d0a3209383e81cdb8c87ab2f913\spring-boot-autoconfigure-2.7.5.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.springframework.boot\spring-boot\2.7.5\fd04e228e6e21b7ad13c10ae29afd31868d842e5\spring-boot-2.7.5.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.springframework.boot\spring-boot-starter-logging\2.7.5\61f4c53e35baa31a269bbeb7bb9d5e781448feef\spring-boot-starter-logging-2.7.5.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\jakarta.annotation\jakarta.annotation-api\1.3.5\59eb84ee0d616332ff44aba065f3888cf002cd2d\jakarta.annotation-api-1.3.5.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.springframework\spring-core\5.3.23\91407dc1106ea423c44150f3da1a0b4f8e25e5ca\spring-core-5.3.23.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.yaml\snakeyaml\1.30\8fde7fe2586328ac3c68db92045e1c8759125000\snakeyaml-1.30.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.apache.tomcat.embed\tomcat-embed-websocket\9.0.68\15fc94001bb916a808631422a6488a678496ef94\tomcat-embed-websocket-9.0.68.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.apache.tomcat.embed\tomcat-embed-core\9.0.68\caafeb87d6ff30adda888049c9b81591c7cc20d1\tomcat-embed-core-9.0.68.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.apache.tomcat.embed\tomcat-embed-el\9.0.68\296afe7483256960d7ebdd8dcb4b49775d7cb85f\tomcat-embed-el-9.0.68.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.springframework\spring-context\5.3.23\530b36b2ce2c9e471c6a260c3f181bcd20325a58\spring-context-5.3.23.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.springframework\spring-expression\5.3.23\3a676bf4b9bc42bd37ab5ad264acb6ceb63397a2\spring-expression-5.3.23.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.springframework\spring-aop\5.3.23\30d0034ba29178e98781d85f51a7eb709a628e9b\spring-aop-5.3.23.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.springframework\spring-beans\5.3.23\3bdefbf6042ed742cbe16f27d2d14cca9096a606\spring-beans-5.3.23.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\com.fasterxml.jackson.core\jackson-annotations\2.13.4\858c6cc78e1f08a885b1613e1d817c829df70a6e\jackson-annotations-2.13.4.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\com.fasterxml.jackson.core\jackson-core\2.13.4\cf934c681294b97ef6d80082faeefbe1edadf56\jackson-core-2.13.4.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\ch.qos.logback\logback-classic\1.2.11\4741689214e9d1e8408b206506cbe76d1c6a7d60\logback-classic-1.2.11.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.apache.logging.log4j\log4j-to-slf4j\2.17.2\17dd0fae2747d9a28c67bc9534108823d2376b46\log4j-to-slf4j-2.17.2.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.slf4j\jul-to-slf4j\1.7.36\ed46d81cef9c412a88caef405b58f93a678ff2ca\jul-to-slf4j-1.7.36.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.springframework\spring-jcl\5.3.23\3c7eb5fcca67b611065f73ff4325e398f8b051a3\spring-jcl-5.3.23.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\ch.qos.logback\logback-core\1.2.11\a01230df5ca5c34540cdaa3ad5efb012f1f1f792\logback-core-1.2.11.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.slf4j\slf4j-api\1.7.36\6c62681a2f655b49963a5983b8b0950a6120ae14\slf4j-api-1.7.36.jar;C:\Users\sinar\.gradle\caches\modules-2\files-2.1\org.apache.logging.log4j\log4j-api\2.17.2\f42d6afa111b4dec5d2aea0fe2197240749a4ea6\log4j-api-2.17.2.jar com.codestates.seb.httpstestproject.HttpstestprojectApplication

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v2.7.5)

2022-11-21 14:14:51.550  INFO 16316 --- [           main] c.c.s.h.HttpstestprojectApplication      : Starting HttpstestprojectApplication using Java 11.0.16 on LAPTOP-1SEJBBEL with PID 16316 (C:\Users\sinar\Desktop\BootCamp\Spring\httpstestproject\build\classes\java\main started by sinar in C:\Users\sinar\Desktop\BootCamp\Spring\httpstestproject)
2022-11-21 14:14:51.553  INFO 16316 --- [           main] c.c.s.h.HttpstestprojectApplication      : No active profile set, falling back to 1 default profile: "default"
2022-11-21 14:14:52.202  INFO 16316 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (https)
2022-11-21 14:14:52.209  INFO 16316 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2022-11-21 14:14:52.209  INFO 16316 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.68]
2022-11-21 14:14:52.294  INFO 16316 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2022-11-21 14:14:52.294  INFO 16316 --- [           main] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 706 ms
2022-11-21 14:14:52.836  INFO 16316 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (https) with context path ''
2022-11-21 14:14:52.849  INFO 16316 --- [           main] c.c.s.h.HttpstestprojectApplication      : Started HttpstestprojectApplication in 1.628 seconds (JVM running for 2.872)

Process finished with exit code 130
```

<p align="center">
    <img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcjAVRQ%2FbtrRJQesWEO%2FQRiHoFh8ZO9vVhe3vPjMKK%2Fimg.png" alt=""/>
</p>