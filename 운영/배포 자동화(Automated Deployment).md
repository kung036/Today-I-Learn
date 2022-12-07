# **배포 자동화(Automated Deployment)**

***

## **배포 자동화(Automated Deployment)**

- 간단한 명령어나 클릭으로 배포를 자동으로 진행
- 필요 이유
    - 반복적인 배포를 자동화함으로써 시간 절약
    - 휴먼 에러(Human Error : 사람의 실수로 인해 발생하는 에러) 방지

## **배포 자동화 파이프라인**

- `배포 자동화의 파이프라인` : 코드 관리부터 서비스 배포 과정을 연결하는 구조
- 상황에 따라서 파이프라인 세분화 및 간소화 가능
- 파이프라인 흐름
    > - Source 단계 : 원격 저장소의 소스 코드가 변경되면 Build 단계로 소스 코드 전달
    > - Build 단계 : 소스 코드의 컴파일, 빌드, 테스트를 진행 및 가공해서 Deploy 단계로 결과물 전달
    > - Deploy 단계 : 사용자에게 제공 중인 서비스에 변경사항을 반영

## **AWS 개발자 도구**

- <u>AWS에서 제공하는 개발자 도구의 서비스</u>를 이용해서 배포 자동화 파이프라인 구축
- CodeCommit
  > - Source 단계에서 사용
  > - 버전 관리 도구
  > - 보안에 강점을 가진 서비스
- CodeBuild
  > - Build 단계에서 사용
  > - unit test, compile, build와 같이 필수적으로 실행해야 되는 작업을 명령어를 통해서 실행
- CodeDeploy
  > - Deploy 단계에서 사용
  > - 실시간으로 변경 사항 전달
- CodePipeline
  > - Pipeline의 각 단계들을 연결하는 파이프라인 구축에 사용

<p align="center">
    <img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F9aBEp%2FbtrS0Lcs6u2%2F7VD01iyd7lhhKcNl4Gdkp1%2Fimg.jpg" alt=""/>
</p>