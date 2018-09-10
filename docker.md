# Docker

## Install

* Ubuntu

```bash
sudo apt-get update
sudo apt-get install docker.io -y
sudo service docker start
```

## Create Container

### HelloWorld

```bash
docker run ubuntu:16.04 /bin/echo "Hello World."
```

### 交互式容器

```bash
docker run -i -t <repo>:<tag> <命令>
# example
docker run -i -t ubuntu:16.04 /bin/bash
# -i interactive 允许和容器的 stdin 交互
# -t terminal 指定一个终端
# exit
exit
```

### 后台模式 

```bash
docker run -d <repo>:<tag> <command>
#example
docker run -d ubuntu:16.04 /bin/sh -c "while true; do echo hello docker; sleep 2; done"
```

## Manage Container

```bash
# 查看运行中的容器
docker ps
# 查看所有容器
docker ps -a
# 查看容器内的标准输出
docker logs <container_id>
docker logs <container_name>
# 停止/启动容器
docker stop/start <container_id>
docker stop/start <container_name>
# 查看容器内进程
docker top <name/id>
# 查看容器配置等信息
docker inspect <name/id>
# 删除容器(必须先停止容器然后才能删除)
docker rm <name/id>
# 重命名容器
--name <name>
# 进入运行中的容器
docker attach <id>
# 创建但是不启动
docker create
# 阻塞到一个容器，直到他停止运行
docker wait
# 在容器里执行一条命令
docker exec
```

## Container Usage

#### 映射端口

```bash
# 自动映射端口
-P
# 映射指定端口
-p <ipaddress>:<outsideport>:<insideport>
# 查看容器端口映射状态
docker port <id>
docker port <name>
```

#### 镜像管理

```bash
# 列出镜像
docker images
# 获取镜像
docker pull <repo>:<tag>
# 搜索镜像
docker search <key_word>
# 更新镜像
docker commit -m="<description>" -a="<creator>" <id> <image_name>
# 删除镜像
docker rmi <name>
```

#### 构建镜像

* Dockerfile

  ```dockerfile
  # 从一个基础镜像构建新镜像
  FROM ubuntu:16.04
  # 维护者信息
  MAINTAINER Yorling "i@yorling.com"
  # 环境变量
  ENV TES_ENV qaq
  
  # 非交互式执行命令
  RUN apt-get -y update
  # 添加文件到镜像内，SRC 可以为 url
  ADD PATH_SRC PATH_TO
  # 设置工作目录
  WORKDIR path
  # 设置用户 id
  USER nginx
  # 设置 volume 挂载
  VOLUME ['/path']
  # 暴露端口
  EXPOSE 80
  EXPOSE 22
  # 设置 docker 创建和启动时执行的命令
  CMD /usr/sbin/sshd -D
  ```

* Build

  ```bash
  docker build -t <name> <dockerfile_path>
  docker tag <id> <tag>
  ```

* Export

  ```bash
  docker export <id> > docker.tar
  docker save <image> | bzip2 -9 -c > path/name.tar.bz2
  bzip2 -d -c < path/name.tar.bz2 | docker load
  ```
