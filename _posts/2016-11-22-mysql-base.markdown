---
layout : post
title : MySQL] 기본 Query
category : mysql
---

## DB 생성
    mysql> create database DB명 default character set utf8;

## 사용자 생성
    mysql> create user '아이디'@'%' identified by '비밀번호';
    mysql> create user '아이디'@'localhost' identified by '비밀번호';

## 사용자에게 권한 부여
    mysql> grant all privileges on *.* to '아이디'@'%';

특정 DB로만 하고 싶다면 `*.*` 부분을 `DB 이름.*` 으로 변경하면 된다.

## DB 사용
    mysql> use DB명;
    
## Insert
    mysql> insert into 테이블명 (컬럼명, 컬럼명) values(컬럼 값, 컬럼값);

## Select
    mysql> select * from 테이블명 where 컬럼명 = 조건;
    
## Update
    mysql> update 테이블명 set 컬럼명 = 변경 사항 where 컬럼명 = 조건;

## Delete
    mysql> delete from 테이블명 where 컬럼명 = 조건;