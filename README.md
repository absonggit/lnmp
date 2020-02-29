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
IMAGE=nginx-php:v1
CONTAINER_NAME=nginx-php
PORT=8888
NGINX_CONF_DIR=/root/lnmp/nginx/conf
PHP_ETC_DIR=/root/lnmp/php/etc
WEB_HOME_DIR=/root/lnmp/wwwroot
--------------------------------------

# build 镜像并启动
docker-compose up -d
```