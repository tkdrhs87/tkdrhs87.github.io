---
layout : post
title : CentOS7] rbenv로 Ruby 설치
category : centos
---

## 설치 Package

    # yum install -y git-core zlib zlib-devel gcc-c++ patch readline readline-devel libyaml-devel libffi-devel openssl-devel make bzip2 autoconf automake libtool bison curl sqlite-devel

설치 후

    # cd ~
    # git clone git://github.com/sstephenson/rbenv.git .rbenv
    # echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile
    # echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
    # git clone git://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build
    # echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bash_profile
    # source ~/.bash_profile

## rbenv로 설치 할 수 있는 ruby 목록

    # rbenv install -l

## rbenv로 ruby 설치

    # rbenv install 2.3.0
    # rbenv rehash

## rbenv로 ruby 적용

    # rbenv global 2.3.0
    # ruby -v

## ruby bundler 설치

    # gem install bundler --no-rdoc --no-ri