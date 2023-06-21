#Python 3，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    apt-get install libssl1.1=1.1.1n-0+deb11u4 python3 python3-distutils libpq-dev default-libmysqlclient-dev -y &&\
    curl https://bootstrap.pypa.io/get-pip.py | python3 &&\
    pip install virtualenv

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD pip -V
