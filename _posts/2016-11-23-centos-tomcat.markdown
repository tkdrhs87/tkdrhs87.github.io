---
layout : post
title : CentOS7] Tomcat 설치
category : centos
---

## Tomcat 다운로드
    # wget http://apache.mirror.cdnetworks.com/tomcat/tomcat-8/v8.5.8/bin/apache-tomcat-8.5.8.tar.gz
    # tar xvzf apache-tomcat-8.5.8.tar.gz
    # mv apache-tomcat-8.5.8 tomcat
    
## Tomcat 구동
    # cd tomcat/bin/
    # ./startup.sh

## Tomcat 확인
    # netstat -anp | grep LISTEN | grep java