#Python 3.9，基于 dujunio/debian

FROM dujunio/debian
MAINTAINER dujun

ADD data.txz /

RUN apt-get update -y &&\
    apt-get install python3 python3-distutils  libssl1.1 libpq-dev default-libmysqlclient-dev -y &&\
    curl https://bootstrap.pypa.io/get-pip.py | python3 &&\
    pip install virtualenv pipenv

ENTRYPOINT /entrypoint

HEALTHCHECK --interval=1s --timeout=5s --retries=3 CMD pip -V
