---
layout : post
title : CentOS7] Apach 설치
category : centos
---

## Apache 다운로드
    # wget http://apache.mirror.cdnetworks.com/httpd/httpd-2.2.31.tar.gz
    # tar xvzf httpd-2.2.31.tar.gz
    
## Apr 다운로드 및 설치
    # wget http://apache.mirror.cdnetworks.com/apr/apr-1.5.2.tar.gz
    # tar xvzf apr-1.5.2.tar.gz
    # cd apr-1.5.2
    # ./configure
    # make
    # make install
    # make clean
    
## Apr-util 다운로드 및 설치
    # wget http://apache.mirror.cdnetworks.com/apr/apr-util-1.5.4.tar.gz
    # tar xvzf apr-util-1.5.4.tar.gz
    # cd apr-util-1.5.4
    # ./configure --with-apr=/usr/local/apr
    # make
    # make install
    # make clean
    
## Pcre 다운로드 및 설치
    # wget http://jaist.dl.sourceforge.net/project/pcre/pcre/8.39/pcre-8.39.tar.gz
    # tar xvzf pcre-8.39.tar.gz
    # cd pcre-8.39
    # ./configure --prefix=/usr/local/pcre
    # make
    # make install
    # make clean
    
## Apache 설치 
    # cd httpd-2.2.31
    # ./configure --prefix=/usr/local/apache --enable-http --enable-info --enable-cgi --enable-so --with-pcre=/usr/local/pcre
    # make
    # make install
    # make clean
    
## Apache 구동
    # cd /usr/local/apache/bin
    # ./httpd -k start
    
## Apache 확인
    # netstat -anp | grep LISTEN | grep httpd