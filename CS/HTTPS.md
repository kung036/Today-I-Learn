# **HTTPS**

## **HTTPS**

- **HTTPS(Hyper Text Transfer Protocol Secure Socket layer)** : HTTP 프로토콜 요청을 SSL 또는 TLS 알고리즘을 이용해서 암호화하여 전송(HTTP +
  Secure)
- 목적
    - 암호화 : 서버와 클라이언트 사이에 주고받는 정보를 탈취해도 내용을 알 수없도록 비대칭키를 이용해서 암호화하기
- 특징
    - 인증서(Certificate)
        - 데이터를 전송한 곳의 신원을 보장하는 것(= 전자 서명)
        - 응답에 확인한 도메인과 인증서에 작성된 도메인이 같다면 신원 보장
        - 개인키를 이용해서 인증서를 암호화하고 공개키를 이용해서 복호화
    - CA(Certificate Authority)
        - 공인 인증서를 발급하는 기관
        - 기관마다 다른 인증서를 발급
        - CA에서 발급한 인증서는 CA의 비밀키로 암호화를 하고, CA의 공개키를 이용해서 복호화
    - 비대칭키 암호화
        - 공개키(public key)를 이용해서 데이터를 암호화하고, 개인키(private key)를 이용해서 데이터를 복호화하는 암호화 방식
        - 한 쌍의 키 : 공개키(public key), 비밀키(private key)
        - 공개키를 이용해서 데이터 전송한 곳의 신원 보장
- 특성
    - 기밀성(privacy) : 데이터 유출되지 않는 성격
    - 무결성(integrity) : 데이터가 조작되지 않는 성격
- 통신 과정
    - **① 연결 요청(랜덤 데이터)**
        - client는 server와 통신을 하기 위해서 렌덤으로 생선된 데이터를 server에 전송
    - **② 전달(랜덤 데이터, 공개키, 인증서)**
        - server는 client로부터 받은 랜덤 데이터, server임을 인증하는 인증서, 비대칭키(공개키, 개인키) 중 공개키를 client에게 전송
    - **③ 전달(암호화된 세션키)**
        - client는 데이터 암복호화하기 위한 대칭키인 세션키를 server로부터 받은 공개키를 이용해서 암호화해서 server에게 전송
    - **④ HTTPS 통신**
        - client와 server는 통신을 할 때 세션키를 통해서 데이터 암복호화를 함

<p align="center">
    <img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fbv87zs%2FbtrRAMCkIDc%2F5t8AoGOF8KTm0xVyfFOeM1%2Fimg.png" alt=""/>
</p>
