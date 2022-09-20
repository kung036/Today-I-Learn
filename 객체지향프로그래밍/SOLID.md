# **객체지향프로그래밍 설계원칙(SOLID)**

>S : SRP(단일 책임 원칙)  
O : OCP(개방 폐쇄 원칙)  
L : LSP(리스코프 치환 원칙)  
I : ISP(인터페이스 분리 원칙)  
D : DIP(의존 역전 원칙)  

1.  **단일 책임 원칙(SRP, Single Responsibility Principle)**  
    -  하나의 모듈은 하나의 책임만을 가진다.
2.  **개방 폐쇄 원칙(OCP, Open-Closed Principle)**  
    -  확장에 열려 있다 : 프로그램의 동작 추가 및 기능 확장 가능  
    -  변경에 닫혀 있다 : 코드를 수정하지 않고 프로그램의 동작 추가 및 변경 가능
3.  **리스코프 치환 원칙(LSP, Liskov Substitution Principle)**  
    -  다형성(객체의 하위 타입은 상위 타입으로 대체 가능)
4.  **인터페이스 분리 원칙(ISP, Interface Segregation Principle)**  
    -  여러 개의 범용 인터페이스보다 하나의 인터페이스 구조가 나음
5.  **의존 역전 원칙(DIP, Dependency Inversion Principle)**  
    -  추상화에 의존하고 구체화에 의존하지 않는 설계 원칙  
    -  하위 레벨 모듈의 변경이 상위 레벨 모듈의 변경을 요구하지 않음
