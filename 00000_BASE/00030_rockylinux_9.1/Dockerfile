#Rocky Linux 9.1，基于官方镜像 rockylinux:9.1

FROM rockylinux:9.1
MAINTAINER dujun

ENV LANG=en_US.utf8 \
    LC_ALL=C.UTF-8 \
    TZ=Asia/Shanghai \
    HOSTNAME=osexample

RUN sed -e 's|^mirrorlist=|#mirrorlist=|g' -e 's|^#baseurl=http://dl.rockylinux.org/$contentdir|baseurl=https://mirrors.aliyun.com/rockylinux|g' -i.bak /etc/yum.repos.d/*.repo &&\
    yum install procps net-tools -y
