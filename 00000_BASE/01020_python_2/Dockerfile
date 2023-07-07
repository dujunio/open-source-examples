#Python 2，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    apt-get install libssl1.1=1.1.1n-0+deb11u4 -y --allow-downgrades &&\
    apt-get install python2 -y &&\
    curl https://bootstrap.pypa.io/pip/2.7/get-pip.py | python2 &&\
    pip install virtualenv

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD pip -V
