# mysql

## 데이터 베이서의 목적
- 데이터베이스와 스프래드시트의 유사점과 차이점을 통해 데이터베이스를 이해해보자.
- 데이터 베이스 : 컴퓨터 언어를 통해 제어가 가능하다.
- 스프레드시트 : UI를 통해 제어가 가능하다.
- 공통점 : 둘다 하고자 하는 기능과 목표가 비슷하다. (검색, 정렬 ...)
  
## mysql 구조
- 데이터를 기록하는 최종적인 장소 : 표 (스프레드시트와 비슷한 구조를 가지고 있음)
- 데이터 베이스 : 표들을 다른 표들과 구분지어 햇갈리지 않게 해주는 일종의 폴더 (햇갈리지 않게 스키마 라는 표현을 쓸 예정)
- 데이터 베이스 서버 : 스키마들을 저장해놓은 곳 (mysql ...)

## mysql 서버 접속
- ./mysql -uroot -p: 기본 유저로 사용하겠다는 뜻 + 비밀번호를 치면 접속가능
- winpty 명령어를 쓰면 gitbash에서도 쓸 수 있다.

## mysql 스키마의 사용
- CREATE DATABASE opentutorials; (database 생성하는 방법)
- DROP DATABASE opentutorials; (database 제거하는 방법)
- SHOW {DATABASES | SCHEMAS} (database 보여주는 방법)
- USE opentutorials (database 를 사용하겠다고 설정하는 방법)

## SQL과 테이블 구조
- SQL : Structured Query Language
- 관계형 데이터가 표를 이용하여 정보를 정리하는데 이러한 정리를 의미하는 것 : Structured
- 데이터베이스에게 질문한다는 뜻을 내포하는 Query
- SQL의 특징 : 컴퓨터 언어중에서 제일 쉽다. (html급), 매우 중요하다. (대부분의 데이터 베이스를 SQL로 이용 가능)
- table (표), row, record (행), column(열), row, record -> 데이터 하나 하나, column -> 데이터의 구조

## MySQL 테이블의 생성
- https://www.w3schools.com/mysql/mysql_datatypes.asp (데이터 타입 정리)
- CREATE TABLE topic(
- id INT(11) NOT NULL AUTO_INCREMENT,  (mysql은 column을 지정해 줄 때 데이터 타입을 정해주어야 한다.)
- title VARCHAR(100) NOT NULL, 
- description TEXT NULL,
- created DATETIME NOT NULL,
- author VARCHAR(30) NULL,
- profile VARCHAR(100) NULL,
- PRIMARY KEY(id) (중복을 관리하기 위해 설정하는 것이다.)
- );
- ALTER TABLE table_name ADD COLUMN column_name data_type; (column을 추가)
- ALTER TABLE table_name CHANGE column_name column_name new_position data_type; (column의 위치를 바꿈)
- ex) ALTER TABLE employees CHANGE age age AFTER salary INT(11);

## CRUD
- CREATE
- READ
- UPDATE
- DELETE

## SQL의 INSERT 구문
- INSERT INTO table_name (column1, column2, column3 ...);
- VALUES (value1, value2, value3, ...);
- SHOW TABLES; (TABLE을 볼 수 있음)
- DESC topic; (topic 테이블의 구조를 볼 수 있음)
- INSERT INTO topic (title, description, created, author, profile) VALUES('MySQL', 'MySQL is ...', NOW(), 'egoing', 'developer');
- SELECT * FROM topic; (특별한 언급이 없으면 모든 데이터를 갖고 옴)

## SQL의 SELECT 구문
- SELECT * FROM topic;
- SELECT id, title, description FROM topic; (특정 column만 출력 함)
- MySQL SELECT syntax 공식문서 봐보기
- SELECT id, title, created, author, FROM topic WHERE author = 'egoing'; (특정 데이터만 갖고 있는 데이터를 갖고옴)
- SELECT id, title, created, author FROM topic WHERE author = 'egoing'   ORDER BY id DESC; (정렬)
- SELECT id, title, created, author FROM topic WHERE author = 'egoing'   ORDER BY id DESC LIMIT 2; (2개만 갖고옴)

## SQL의 UPDATE 구문
- UPDATE table_reference SET assignment_list
- assignment : col_name = value
- UPDATE topic SET description = 'Oracle is ???', title = 'Oracle' WHERE id = 2;

## SQL의 DELETE 구문
- DELETE FROM topic WHERE id = 5;

## 수업의 정상
- 기술을 만나면 본질과 혁신이 무엇인지 분리하려고 노력하면 기술을 판단하는데 도움이 된다.
- 혁신 : Relational, 본질 : Database (CRUD)

## 관계형 데이터베이스의 필요성
- 