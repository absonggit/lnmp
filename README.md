# Docker 部署lnmp环境
#### 安装docker
```bash
curl -fsSL https://get.docker.com | sh -
```
#### 安装docker-compese
```bash
curl -s https://raw.githubusercontent.com/absonggit/tools/master/docker_compose/install_docker_compose.sh |sh
```
#### 拉取代码
```bash
git clone https://github.com/absonggit/lnmp.git
```
#### 修改.env配置
```ini
# 设置全局安装目录
HOME_DIR=lnmp
# nginx & php
NGINX_IMAGE=nginx-php:v1
NGINX_PORT=8888

# redis
REDIS_IMAGE=redis:v1
REDIS_PORT=6379

# mysql
MYSQL_IMAGE=mysql:5.6.47
MYSQL_PORT=3306
MYSQL_ROOT_PASSWORD=123456
```
#### build 镜像并启动
```bash
docker-compose up -d
```
