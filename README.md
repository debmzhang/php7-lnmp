##PHP+NGINX docker-compose
* 基于 centos:centos7 官方镜像
* 使用 163 源
* php 版本为 [7.4.13](https://www.php.net/distributions/php-7.4.13.tar.gz)
* nginx 始终为最新版本
* 数据库集成 mysql5.7 redis6.0.9

##目录说明
* conf.d
    * nginx 的配置文件放在这里, default.conf 只是一个参考例子, 根据需要自行配置
* etc
    * php nginx 的配置文件要放于这里, 可在 docker-compose.yml 文件中添加 volumns 进行映射
* logs
    * php nginx 的日志文件
* tmp
    * 映射容器的 tmp 目录
* www
    * 放置项目源码
* data
    * 存储 mysql `data/mysql`  redis `data/redis`  数据

##使用
* 安装 [docker](https://docs.docker.com/get-docker/) 与 [docker-compose](https://yeasy.gitbook.io/docker_practice/compose/install)
* sudo docker-compose up -d

##注意事项
> `docker-compose.yml` 中涉及到使用变量的地方需自行添加 `.env` 文件, 并在该文件中配置变量
> 比如 `docker-compose.yml` 中的 ${mysql_root_password} 可以在 `.env` 文件中配置 `mysql_root_password=123123`
> [.env说明文档](https://docs.docker.com/compose/env-file/)
