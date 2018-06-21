---
layout: post
title: docker-compose配置
date: 2018-06-21 18:00:00
categories: Software
tags: 博客
excerpt: Software
---

参考链接:[https://docs.docker.com/compose/gettingstarted/](https://docs.docker.com/compose/gettingstarted/)

##### docker compose ?

docker-compose 是一个用来把 docker 自动化的东西。
有了 docker-compose 你可以把所有繁复的 docker 操作全都一条命令，自动化的完成。

##### 环境

确保您已经安装了[Docker Engine](https://docs.docker.com/install/)和[Docker compose](https://docs.docker.com/compose/install/)。您不需要安装Python或Redis，因为它们都由Docker images提供。

##### docker-compose 常用命令

```
Commands:
  build              Build or rebuild services
  bundle             Generate a Docker bundle from the Compose file
  config             Validate and view the compose file
  create             Create services
  down               Stop and remove containers, networks, images, and volumes
  events             Receive real time events from containers
  exec               Execute a command in a running container
  help               Get help on a command
  kill               Kill containers
  logs               View output from containers
  pause              Pause services
  port               Print the public port for a port binding
  ps                 List containers
  pull               Pull service images
  push               Push service images
  restart            Restart services
  rm                 Remove stopped containers
  run                Run a one-off command
  scale              Set number of containers for a service
  start              Start services
  stop               Stop services
  top                Display the running processes
  unpause            Unpause services
  up                 Create and start containers
  version            Show the Docker-Compose version information
```

- 解释一下
```
build 构建或重建服务
help 命令帮助
kill 杀掉容器
logs 显示容器的输出内容
port 打印绑定的开放端口
ps 显示容器
pull 拉取服务镜像
restart 重启服务
rm 删除停止的容器
run 运行一个一次性命令
scale 设置服务的容器数目
start 开启服务
stop 停止服务
up 创建并启动容器
```

##### docker-compose 如何配置
先看看一个 docker-compose.yml
```
version: '2'
services:
    nginx:
            image: bitnami/nginx:latest
            ports:
                - '80:80'
                - '1443:443'
            volumes:
                - /root/wp_yunlan/nginx/:/bitnami/nginx/
    mariadb:
            image: bitnami/mariadb:latest
            volumes:
                - /root/wp_yunlan/mariadb:/bitnami/mariadb
    wordpress:
            image: bitnami/wordpress:latest
            depends_on:
                - mariadb
                - nginx
            environment:
                - WORDPRESS_USERNAME=neptunemoon    #这个账户你是自己设定的
                - WORDPRESS_PASSWORD=123123         #这个密码是你自己设定的
            ports:
                - '8080:80'
                - '8081:443'
            volumes:
                - /root/wp_yunlan/wordpress:/bitnami/wordpress
                - /root/wp_yunlan/apache:/bitnami/apache
                - /root/wp_yunlan/php:/bitnami/php
```
- nginx 和 mariadb，wordpress 是要启动的三个服务
  顺序不是重要的,我们看见wordpress中有个 depends_on: 的属性
- depends_on: 依赖
  代表wordpress 依赖于
  ```
  - mariadb
  - nginx
  ```
  两个服务， 所以他们两个会先启动
- image: 镜像
  就是你的 docker 镜像
  我们用
  ```
  docker search mariadb
  ```
  找到我们需要的镜像
- environment 环境变量
  这个是在好理解不过的了。
  不过这和我们程序语言设计层面的还是不一样的，这个是容器层面的环境变量。
  如果我们写程序做一些逻辑判断的时候，肯定会使用
  比如我们判断现在的编译器，我们会使用
  #if __GNUC__ 或者 #if _MSC_VER
  相应的，我们的容器里面肯定也有这样的逻辑，我们经常使用环境变量来传值，或者定义一个行为。写过程序的人都懂。
- ports 端口映射
  映射本机还有镜像的端口。这个没有什么好说的。
- volumes 文件映射
  有两种格式，
  可以对应 docker 操作中的 -v my/path/:/docker/path
  还可以使用单方面的 -v /path 
  这样的话 就相当于 一个匿名映射， 其实还是在本机有对应目录的。

  使用docker inspect -f {{.Volumes}} /path 可以看到详细信息
- docker-compose 需要注意的
  1、不要把 docker 当做数据容器来使用，数据一定要用 volumes 放在容器外面
  2、不要把 docker-compose 文件暴露给别人， 因为上面有你的服务器信息
  3、多用 docker-compose 的命令去操作， 不要用 docker 手动命令&docker-compose 去同时操作
  4、写一个脚本类的东西，自动备份docker 映射出来的数据。
  5、不要把所有服务都放在一个 docker 容器里面