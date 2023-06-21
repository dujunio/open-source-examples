#Ubuntu 18.04，基于官方镜像 ubuntu:18.04

FROM ubuntu:18.04
MAINTAINER dujun

ENV DEBIAN_FRONTEND=noninteractive \
    LANG=en_US.utf8 \
    LC_ALL=C.UTF-8 \
    TZ=Asia/Shanghai \
    HOSTNAME=osexample

RUN echo "deb http://mirrors.aliyun.com/ubuntu/ bionic main universe restricted multiverse\ndeb http://mirrors.aliyun.com/ubuntu/ bionic-security main universe restricted multiverse\ndeb http://mirrors.aliyun.com/ubuntu/ bionic-updates main universe restricted multiverse\ndeb http://mirrors.aliyun.com/ubuntu/ bionic-backports main universe restricted multiverse\ndeb-src http://mirrors.aliyun.com/ubuntu/ bionic main universe restricted multiverse\ndeb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main universe restricted multiverse\ndeb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main universe restricted multiverse\ndeb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main universe restricted multiverse" > /etc/apt/sources.list &&\
    apt-get update -y &&\
    apt-get install -y apt-utils tzdata curl net-tools &&\
    dpkg-reconfigure -f noninteractive tzdata && \
    echo $TZ > /etc/timezone
