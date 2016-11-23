---
layout : post
title : CentOS7] Firewall 설치 및 설정
category : centos
---

## Firewall 설치

    # yum install -y firewalld

## 포트 허용

    # firewall-cmd --permanent --zone=public --add-port=3306/tcp
    # firewall-cmd --reload