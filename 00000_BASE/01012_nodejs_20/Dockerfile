#Node.js 20

FROM dujunio/debian:12.4
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    curl -sL https://deb.nodesource.com/setup_20.x | bash &&\
    apt-get install nodejs -y &&\
    npm config set registry https://registry.npmmirror.com/ &&\
    npm i -g npm &&\
    npm i -g serve pm2 pnpm

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD node -v
