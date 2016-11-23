---
layout : post
title : CentOS7] Minimal
category : centos
---

## 기본 네트워크 설정

![cm_01](https://raw.githubusercontent.com/tkdrhs87/tkdrhs87.github.io/master/_images/20161121/cm_01.png)

    # cd /etc/sysconfig/network-scripts
    # vi ifcfg-eno16777736

ifcfg-eno16777736 파일명은 설치 할때 마다 다르다.

![cm_02](https://raw.githubusercontent.com/tkdrhs87/tkdrhs87.github.io/master/_images/20161121/cm_02.png)

DHCP 사용시 ONBOOT=no -> ONBOOT=yes

    # service network restart

## SSH 추가

    # yum install -y openssh-server
    # service sshd start
    # chkconfig sshd on

## IFCONFIG 추가

    # yum install -y net-tools

## Update

	# yum update -y