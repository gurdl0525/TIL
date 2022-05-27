# DB-명렁어
<br>&nbsp;

# docker
+ docker 이미지 불러오기
```
docker pull mysql   
```
위와 같이 다운로드 하게 되면 자동으로 최신버전으로 다운받게 된다.<br>따라서 버전을 지정해 주고 싶으면 아래 명령어를 사용한다.
```
docker pull mysql:버전
```
+ MySQL(DB) 실행
```
docker run --사용자가 사용할 이름 mysql-container -e MYSQL_ROOT_PASSWORD=사용자가 사용할 비번 -d -p 3306:3306 mysql:latest
```
+ 컨테이너 시작 명령어
```
docker start mysql-container
```
+ 컨테이너 중지 명령어
```
docker stop mysql-container
```
+ 컨테이너 재시작 명령어
```
docker restart mysql-container
```

---
+ 컨테이너 접속
```
docker exec -it mysql-container bash
```

<img src="%ED%99%94%EC%82%B4%ED%91%9C.png" width="150" height="150">

```
docker exec -it mysql-container bash
root@dc557b92f573:
```
<img src="%ED%99%94%EC%82%B4%ED%91%9C.png" width="150" height="150">

```
docker exec -it mysql-container bash
root@dc557b92f573:/# mysql -u root -p
```

<img src="%ED%99%94%EC%82%B4%ED%91%9C.png" width="150" height="150">

```
docker exec -it mysql-container bash
root@dc557b92f573:/# mysql -u root -p
Enter password:
```

mysql실행 때 설정한 비밀번호 입력

<img src="%ED%99%94%EC%82%B4%ED%91%9C.png" width="150" height="150">

```
docker exec -it mysql-container bash
root@dc557b92f573:/# mysql -u root -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 9
Server version: 8.0.22 MySQL Community Server - GPL

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.
```

# DDL
## 테이블 생성(CREATE)
```
CREATE TABLE `테이블 이름`(
    `컬럼명1` 데이터 타입,
    `컬럼명2` 데이터 타입,
    `컬럼명3` 데이터 타입
);
```
(Ex)
```
CREATE TABLE `member_table` (
    `id` INT,
    `name` VARCHAR(256),
    `age` INT
);
```
실행 결과
![테이블3](%ED%85%8C%EC%9D%B4%EB%B8%94(3).png)

---
## 테이블 수정(ALTER)
+ 컬럼 추가
```
ALTER TABLE `테이블  이름` ADD `추가할 컬럼명` 데이터 타입;
```
+ 컬럼 수정<br>(데이터 타입 크기 등등을 변경할 수 있음)
```
ALTER TABLE `테이블 이름`
MODIFY COLUMN `수정할 컬럼` varchar(256);
```
+ 컬럼삭제
```
ALTER TABLE `테이블 이름` DROP COLUMN `컬럼 이름`;
```

---
## 테이블 삭제
```
DROP TABLE `테이블 이름`;
```

---
# DML
## INSERT
```
INSERT INTO `테이블 이름`(컬럼1, 컬럼2) VALUES (컬럼1에 넣을 값, 컬럼2에 넣을 값);
```
## SELECT
```
SELECT 추출할 컬럼 FROM `테이블 이름` WHERE (조건문);
```
## UPDATE
```
UPDATE `테이블 이름` SET 컬럼명=컬럼에 넣을 값 WHERE 컬럼명=현재 들어가 있는 값;
```
## DELETE
```
DELETE FROM `테이블 이름` WHERE (조건문);
```