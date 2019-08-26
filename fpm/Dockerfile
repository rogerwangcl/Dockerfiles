FROM centos:latest

RUN yum install --nogpgcheck -y ruby-devel gcc make wget rpm-build rubygems \
    && yum clean all \
    && rm -rf /var/cache/yum

RUN gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/ \
    && echo ':ssl_verify_mode: 0' >> ~/.gemrc \
    && gem install --no-ri --no-rdoc fpm 
