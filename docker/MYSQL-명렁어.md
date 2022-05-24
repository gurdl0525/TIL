# MYSQL-명렁어
# TABLE 명령어
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
# CRUD 명령어
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