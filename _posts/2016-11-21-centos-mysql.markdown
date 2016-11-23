---
layout : post
title : CentOS7] MySQL 설치 및 설정
category : centos
---

## yum Repository 추가

    # rpm -Uvh http://dev.mysql.com/get/mysql-community-release-el7-5.noarch.rpm
    # yum repolist
    
## MySQL 설치

    # yum -y install mysql-community-server
    
## MySQL 설정

    # vi /etc/my.cnf    

위치 : [mysld] 위쪽에 추가

    [client]
    default-character-set = utf8

위치 : [mysqld_safe] 위쪽에 추가

    character-set-client-handshake=FALSE
    init_connect="SET collation_connection = utf8_general_ci"
    init_connect="SET NAMES utf8"
    character-set-server = utf8
    collation-server = utf8_general_ci
    
    [mysqldump]
    default-character-set = utf8
    
    [mysql]
    default-character-set = utf8

## MySQL 서비스 시작

    # /usr/bin/systemctl enable mysqld
    # /usr/bin/systemctl start mysqld
    
## MySQL 보안 설정 (Option)

    # /usr/bin/mysql_secure_installation
    
ROOT 비밀번호 설정<br>
ROOT 제외 다른 유저 삭제<br>
ROOT의 원격 접속 허용<br>
TEST Database 삭제<br>
PRIVILEGES 테이블을 재시작<br>
    
들을 차례대로 진행한다.