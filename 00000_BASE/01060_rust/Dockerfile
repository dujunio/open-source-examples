#Rust，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    apt-get install build-essential -y &&\
    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -yq

ENTRYPOINT /entrypoint
