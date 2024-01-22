#Debian，基于官方镜像 debian:12.4

FROM debian:12.4
MAINTAINER dujun

ENV DEBIAN_FRONTEND=noninteractive \
    LANG=en_US.utf8 \
    LC_ALL=C.UTF-8 \
    TZ=Asia/Shanghai \
    HOSTNAME=osexample

RUN rm -f /etc/apt/sources.list.d/debian.sources &&\
    echo "deb http://mirrors.tencent.com/debian/ bookworm main non-free non-free-firmware contrib\ndeb-src http://mirrors.tencent.com/debian/ bookworm main non-free non-free-firmware contrib\ndeb http://mirrors.tencent.com/debian-security/ bookworm-security main\ndeb-src http://mirrors.tencent.com/debian-security/ bookworm-security main\ndeb http://mirrors.tencent.com/debian/ bookworm-updates main non-free non-free-firmware contrib\ndeb-src http://mirrors.tencent.com/debian/ bookworm-updates main non-free non-free-firmware contrib\ndeb http://mirrors.tencent.com/debian/ bookworm-backports main non-free non-free-firmware contrib\ndeb-src http://mirrors.tencent.com/debian/ bookworm-backports main non-free non-free-firmware contrib" > /etc/apt/sources.list &&\
    apt-get update -y &&\
    apt-get install apt-utils curl procps net-tools vim git -y &&\
    echo "alias l='ls -lahF --color=auto'\nalias ll='ls -lhF --color=auto'\nalias ls='ls -GF --color=auto'" >> /root/.bashrc
