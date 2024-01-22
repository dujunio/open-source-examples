#Debian，基于官方镜像 debian:11.8

FROM debian:11.8
MAINTAINER dujun

ENV DEBIAN_FRONTEND=noninteractive \
    LANG=en_US.utf8 \
    LC_ALL=C.UTF-8 \
    TZ=Asia/Shanghai \
    HOSTNAME=osexample

RUN echo "deb http://mirrors.cloud.tencent.com/debian bullseye main contrib non-free\ndeb http://mirrors.cloud.tencent.com/debian bullseye-updates main contrib non-free" > /etc/apt/sources.list &&\
    apt-get update -y &&\
    apt-get install apt-utils curl procps net-tools vim git -y &&\
    echo "alias l='ls -lahF --color=auto'\nalias ll='ls -lhF --color=auto'\nalias ls='ls -GF --color=auto'" >> /root/.bashrc
