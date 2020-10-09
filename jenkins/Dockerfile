FROM jenkins/jenkins:lts

COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
USER root
ENV  DEBIAN_FRONTEND noninteractive

RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt \
    && apt-get update \
    && apt-get install -y locales \
    && echo "en_US.UTF-8 UTF-8" > /etc/locale.gen \
    && locale-gen en_US.UTF-8 \
    && dpkg-reconfigure locales \
    && /usr/sbin/update-locale LANG=en_US.UTF-8 \
    && ln -snf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime 

ENV LC_ALL en_US.UTF-8
