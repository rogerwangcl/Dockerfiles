FROM centos:7

RUN rm -rf /etc/yum.repos.d/*

ADD custom.repo /etc/yum.repos.d/

RUN sed -i "s/enabled=1/enabled=0/" /etc/yum/pluginconf.d/fastestmirror.conf \
    && sed -i "s/gpgcheck=1/gpgcheck=0/" /etc/yum.conf \
    && yum makecache fast \
    && yum clean all \
    && rm -rf /var/cache/yum \
    && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

ENV LANG=en_US.UTF-8 \
    LANGUAGE=en_US.UTF-8 \
    LC_ALL=en_US.UTF-8
