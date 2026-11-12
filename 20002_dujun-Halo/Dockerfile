#Halo 2.27.2

FROM busybox
MAINTAINER dujun

ADD data.txz /

# halo-2.27.2.jar 约 135MB，超过 GitHub 单文件 100MB 上限，不纳入仓库，
# 改为构建镜像时从官方 Release 下载，并校验 SHA256 保证完整性。
ARG HALO_VERSION=2.27.2
ARG HALO_JAR_SHA256=aa86f2e99b0430bd7a83daae24ad33760f7162154c147b6ff387e98787348d14

RUN mkdir -p /wwwroot/app && \
    wget -q -O /wwwroot/app/halo-${HALO_VERSION}.jar \
        https://github.com/halo-dev/halo/releases/download/v${HALO_VERSION}/halo-${HALO_VERSION}.jar && \
    echo "${HALO_JAR_SHA256}  /wwwroot/app/halo-${HALO_VERSION}.jar" | sha256sum -c -
