#Ubuntu 20.04，基于官方镜像 ubuntu:20.04

FROM ubuntu:20.04
MAINTAINER dujun

ENV DEBIAN_FRONTEND=noninteractive \
    LANG=en_US.utf8 \
    LC_ALL=C.UTF-8 \
    TZ=Asia/Shanghai \
    HOSTNAME=osexample

RUN echo "deb http://mirrors.aliyun.com/ubuntu/ focal main restricted universe multiverse\ndeb http://mirrors.aliyun.com/ubuntu/ focal-security main restricted universe multiverse\ndeb http://mirrors.aliyun.com/ubuntu/ focal-updates main restricted universe multiverse\ndeb http://mirrors.aliyun.com/ubuntu/ focal-proposed main restricted universe multiverse\ndeb http://mirrors.aliyun.com/ubuntu/ focal-backports main restricted universe multiverse" > /etc/apt/sources.list &&\
    apt-get update -y &&\
    apt-get install -y apt-utils tzdata curl net-tools &&\
    dpkg-reconfigure -f noninteractive tzdata && \
    echo $TZ > /etc/timezone
