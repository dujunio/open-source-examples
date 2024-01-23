#Node.js 16

FROM dujunio/debian:11.7
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    curl -sL https://deb.nodesource.com/setup_16.x | bash &&\
    apt-get install nodejs -y &&\
    npm config set registry https://registry.npmmirror.com/ &&\
    npm i -g ts-node serve pm2

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD node -v
