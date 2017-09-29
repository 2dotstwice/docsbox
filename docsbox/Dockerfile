FROM ubuntu:16.04
MAINTAINER Dmitry Veselov <d.a.veselov@yandex.ru>

RUN DEBIAN_FRONTEND=noninteractive apt-get -y update && \
    DEBIAN_FRONTEND=noninteractive apt-get -y --fix-missing --no-install-recommends -q install \
        libffi-dev \
        libmagic-dev \
        libmagickwand-dev \
        libreoffice \
        libreofficekit-dev \
        python3-dev \
        python3-pip \
        git \
        locales && \
    apt-get -y clean && \
    rm -rf /var/lib/apt/lists/* && \
    locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8

ADD . /home/docsbox
WORKDIR /home/
RUN pip3 install -r docsbox/requirements.txt
