FROM alpine:3.10

MAINTAINER roger <wangcl01@missfresh.cn>

# 配置源、时区、安装 jdk tomcat 
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories \
    && apk update \
    && apk add tzdata openjdk8 apr apr-util openssl tomcat-native \
    && /bin/cp -f /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \ 
    && echo "Asia/Shanghai" > /etc/timezone \
    && apk del tzdata \
    && wget http://mirror.bit.edu.cn/apache/tomcat/tomcat-8/v8.5.43/bin/apache-tomcat-8.5.43.tar.gz \
    && tar xzf apache-tomcat-8.5.43.tar.gz -C /usr/local/ \
    && ln -sf /usr/local/apache-tomcat-8.5.43 /usr/local/tomcat \
    && rm -rf apache-tomcat-8.5.43.tar.gz \
    && rm /usr/local/tomcat/bin/*.bat \
    && sed -i 's#protocol="HTTP/1.1"#protocol="org.apache.coyote.http11.Http11AprProtocol"#g' /usr/local/tomcat/conf/server.xml \
    && rm -rf /var/cache/apk/*

# 配置环境变量
ENV CATALINA_HOME="/usr/local/tomcat"
ENV PATH="${CATALINA_HOME}/bin:${PATH}"

# 工作目录
WORKDIR $CATALINA_HOME

# 开放8080端口
EXPOSE 8080
# 执行命令
CMD ["catalina.sh", "run"]
