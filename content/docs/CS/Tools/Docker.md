## 使用Docker提供本项目的Mysql和Redis服务

## Install
https://docs.docker.com/install/linux/docker-ce/centos/

https://blog.csdn.net/weixin_39477597/article/details/87715899

https://blog.csdn.net/weixin_43569697/article/details/89279225

CMD中写windows路径  //c

-v /c\Users\sunhu\Documents\Study\Tool\calibre-web\books

# Docker 启动、重启、关闭
开机自启

systemctl enable docker

systemctl start docker

守护进程重启
systemctl daemon-reload

重启docker服务
systemctl restart docker  /  service docker restart

关闭
docker service docker stop / docker systemctl stop docker



## 停用全部运行中的容器:

docker stop $(docker ps -q)

## 删除全部容器：

docker rm $(docker ps -aq)

## 一条命令实现停用并删除容器：

```
docker stop $(docker ps -q) & docker rm $(docker ps -aq)
```


## 命令
- docker images
- docker search <image_name>
- docker pull <域名>/<namespace>/<repo>:<tag>
- docker rmi  <image>:<tag>
- docker inspect <image_id> 查看容器信息

## 容器命令
- docker create <image_name>
- docker run <image_name>
- docker run ubuntu /bin/echo "Test"
- docker run --name demo -d ubuntu
- docker stop <container_id>
- docker ps 查看运行中的容器
- docker ps -a 列出启动过的容器 可以使用start重新启动
- docker start <container_id> 启动容器
- docker rm <container_id>
- docker rm -f <container_id>
-  *docker container top <container>*
- docker exec <options> <container_id> <command>
  - docker exec -it <container_id> bash 登陆到容器中

## 案例
docker run --name mysqlsvr -p 12345:3306 -e MYSQL_ROOT_PASSWORD=sfy1314 -d mysql

docker run -p 6379:6379 -v $PWD/data:/data -d redis redis-server --appendonly yes

开机自启

docker run --restart=always --name first-mysql -p 12345:3306 -e MYSQL_ROOT_PASSWORD=sfy1314 -d mysql



### MongoDB

docker run --name mongo -p 27017:27017 -v ~/Desktop/docker/mongo:/data/db -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=admin -d mongo

登录到MongoDB容器中

docker exec -it mongo  bash

通过Shell连接MongoDB

mongo -u admin -p admin

### Rdis

获取镜像

docker pull redis

启动Redis

docker run --name redis -d -p 6379:6379 redis



docker exec -it <container_name> redis-cli

### Nginx

 docker run --restart always --name my-nginx -p 80:80 -d nginx

### RabbitMQ

```
#指定版本，该版本包含了web控制页面
docker pull rabbitmq:management
```

```
docker run -d --hostname my-rabbit --name rabbit -e RABBITMQ_DEFAULT_USER=user -e RABBITMQ_DEFAULT_PASS=password -p 15672:15672 -p 5672:5672 rabbitmq:management
```

### ElasticSearch
```
docker run -d -p 9200:9200 elasticsearch
```