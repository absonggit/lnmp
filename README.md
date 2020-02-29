# Docker 部署lnmp环境
```shell
# 安装docker
curl -fsSL https://get.docker.com | sh -

# 安装docker-compese
curl -s https://raw.githubusercontent.com/absonggit/tools/master/docker_compose/install_docker_compose.sh |sh

# 拉取代码
git clone https://github.com/absonggit/lnmp.git

# 修改配置
cd lnmp
vim .env
--------------------------------------
HOME_DIR=lnmp
# nginx & php
NGINX_IMAGE=nginx-php:v1
NGINX_PORT=8888
NGINX_CONF_DIR=/nginx/conf
PHP_ETC_DIR=/php/etc
WEB_HOME_DIR=/wwwroot

# redis
REDIS_IMAGE=redis:v1
REDIS_PORT=6379
REDIS_CONF_FILE=/redis/redis.conf
REDIS_DATA_DIR=/redis/data

# mysql
MYSQL_IMAGE=mysql:5.6.47
MYSQL_PORT=3306
MYSQL_ROOT_PASSWORD=123456
MYSQL_CONF_FILE=/mysql/my.cnf
MYSQL_DATA_DIR=/mysql/data
--------------------------------------

# build 镜像并启动
docker-compose up -d
```