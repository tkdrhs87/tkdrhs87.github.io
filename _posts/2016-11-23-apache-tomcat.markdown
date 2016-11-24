---
layout : post
title : Apache] Tomcat 연동
category : apache
---

## Tomcat Connector 설치 및 설정
    # wget http://apache.mirror.cdnetworks.com/tomcat/tomcat-connectors/jk/tomcat-connectors-1.2.42-src.tar.gz
    # tar xvzf tomcat-connectors-1.2.42-src.tar.gz
    # cd tomcat-connectors-1.2.42-src/native/
    # ./configure --with-apxs=/usr/local/apache/bin/apxs
    # make && make install && make clean
    # cd /usr/local/apache/conf/
    # vi workers.properties

추가 내용

    workers.tomcat_home="/usr/local/tomcat"
    workers.java_home="/usr/local/java"
    ps=/
    worker.list=ajp13
    worker.ajp13.type=ajp13
    worker.ajp13.host=localhost
    worker.ajp13.port=8009

저장후

    # vi mod_jk.conf
    
추가 내용

    <IfModule mod_jk.c>
        JkWorkersFile "/usr/local/apache/conf/workers.properties"
        JkLogFile "/usr/local/tomcat/logs/mod_jk.log"
        JkLogLevel info
        JkAutoAlias "/usr/local/tomcat/webapps"
        JkMount /*.jsp ajp13
        JkMount /*.do ajp13
        JkMount /* ajp13
        #JkMount /servlet/* ajp13
        #JkMount /examples/*.jsp ajp13
        JkLogStampFormat "[%a %b %d %H:%M:%S %Y]"
        JkOptions +ForwardKeySize +ForwardURICompat -ForwardDirectories
        JkRequestLogFormat "%w %V %T"
    </IfModule>

저장후

    # vi httpd.conf

맨 아래로

    LoadModule jk_module modules/mod_jk.so 
    include conf/mod_jk.conf
