# SpringBoot-DB연동
springboot와 데이터 베이스를 연동하는 방법을 알아보자.<br>먼저 스프링 부트 프로젝트를 설정할 때 다음과 같은 드라이버를 추가해준다.

![DB연동](DB%ED%99%98%EA%B2%BD%EC%84%A4%EC%A0%95.png)

그리고 프로젝트를 생성해준다.

![환경](%ED%99%98%EA%B2%BD.png)

1. .properties타입을 yml로 바꾸어준다.<br>후에 다음과 같이 의존성을 추가해준다.

```
spring:
  datasource:
    driver-class-name: com.mysql.cj.jdbc.Driver
    url: jdbc:mysql://localhost:3306/DB이름
    password: 설정했던 비밀번호
    username: root
  jpa:
    show-sql: true
    hibernate:
      ddl-auto: none
```
2. build.gradle파일에 다음과 같이 라이브러리를 다운 받아준다.

![gradle](gradle.png)

3. 엔티티 패키지 추가(객체와는 다른 의미)

![환경2](%ED%99%98%EA%B2%BD(2).png)

4. 엔티티 패키지 아래에 클래스 생성

![엔티티](%EC%97%94%ED%8B%B0%ED%8B%B0.png)

5. <span style="color:yellow">@Entity</span> 어노테이션 추가

![엔티티2](%EC%97%94%ED%8B%B0%ED%8B%B0(2).png)

6. <span style="color:yellow">@Table</span> 어노테이션 추가 및 테이블 지정

![테이블4](%ED%85%8C%EC%9D%B4%EB%B8%94(4).png)

7. 컬럼에 맞춰 변수 생성

![엔티티3](%EC%97%94%ED%8B%B0%ED%8B%B0(3).png)

8.  databases패키지 아래에 SQL폴더 생성 및  sql파일 생성

![sql](sql.png)

9. 데이터 소스 구성 클릭

![sql2](sql(2).png)

10. +버튼 클릭

![데이터 소스](%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EC%86%8C%EC%8A%A4.png)

11. MySQL선택

![데이터 소스2](%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EC%86%8C%EC%8A%A4(2).png)

12. 사용자란에 root입력, 비밀번호란에 설정한 비번입력,<br>데이터베이스란에 데이터 베이스 이름 입력

![데이터소스 3](%EB%8D%B0%EC%9D%B4%ED%84%B0%20%EC%86%8C%EC%8A%A4(3).png)

확인 후 연동 끝