#CentOS 7.9，基于官方镜像 centos:centos7.9.2009

FROM centos:centos7.9.2009
MAINTAINER dujun

ENV LANG=en_US.utf8 \
    LC_ALL=en_US.utf-8 \
    TZ=Asia/Shanghai \
    HOSTNAME=osexample

RUN curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo  &&\
    yum install net-tools -y
