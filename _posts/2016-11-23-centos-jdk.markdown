---
layout : post
title : CentOS7] JDK 설치
category : centos
---

## Bit 확인
    # getconf LONG_BIT
    
JDK를 wget으로 다운로드시에 사이트의 said cookie를 설정할수 없기에  파일을 직접 옮기거나 다른 서버에서 받는다.

## JDK 설치
    # tar xvzf jdk-8u111-linux-x64.tar.gz
    # mv jdk1.8.0_111 /usr/local
    # cd /usr/local
    # ln -s jdk1.8.0_111/ java
    
## JAVA 환경변수 설정
    # vi /etc/profile
    
맨 아래 부분에 

    #JAVA
    JAVA_HOME=/usr/local/java
    CLASSPATH=.:$JAVA_HOME/lib/tools.jar
    PATH=$PATH:$JAVA_HOME/bin
    export JAVA_HOME CLASSPATH PATH

    # source /etc/profile
    # java -vsrsion
    # javac -version