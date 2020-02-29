FROM centos:centos7

# 安装nginx & php
RUN yum install wget -y \
    && wget http://soft.vpser.net/lnmp/lnmp1.6.tar.gz -cO lnmp1.6.tar.gz \
    && tar zxf lnmp1.6.tar.gz \
    && cd lnmp1.6 \
    && LNMP_Auto="y" DBSelect="0" PHPSelect="9" SelectMalloc="1" ./install.sh lnmp

# 安装redis扩展
RUN wget http://pecl.php.net/get/redis-4.0.2.tgz \
    && tar xvf redis-4.0.2.tgz -C /usr/src \
    && cd /usr/src/redis-4.0.2 \
    && phpize && ./configure --with-php-config=/usr/local/php/bin/php-config \
    && make && make install \
    && sed -i '$aextension=/usr/src/redis-4.0.2/modules/redis.so' /usr/local/php/etc/php.ini

WORKDIR /home/wwwroot
EXPOSE 80 443
ADD start.sh /start.sh
CMD ["bash", "/start.sh"]
