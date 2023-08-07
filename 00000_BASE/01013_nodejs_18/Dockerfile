#Node.js 18，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    curl -sL https://deb.nodesource.com/setup_18.x | bash &&\
    apt-get install nodejs -y &&\
    npm config set registry https://registry.npmmirror.com/ &&\
    npm install -g npm &&\
    npm install serve pm2 -g

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD node -v
