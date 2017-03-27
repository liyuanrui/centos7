
### 1、更换国内源
```
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
```

### 2、更新源
```
yum clean all
yum makecache
yum update
```

### 3、安装docker
```
yum -y install docker
```

### 4、启动docker
```
systemctl start docker.service
```

### 5、下载docker镜像
```
docker pull centos
```

### 6、启动docker镜像
```
docker run -d --name test centos
-d   后台运行
-it  进入在线
-v   眏射文件夹  /docker:/docker
-p   眏射端口
```

### 7、运行docker镜像命令
```
docker exec -it test /bin/sh
```

### 8、用于与容器交互的命令
```
$ docker create  # 创建一个容器，但不启动它
$ docker run     #  创建并启动一个容器
$ docker stop    # 停止容器
$ docker start   #  启动容器
$ docker restart # 重启容器
$ docker rm      # 删除容器
$ docker kill    #  给容器发送kill信号
$ docker attach  # 连接到正在运行的容器中
$ docker wait    # 阻塞直到容器停止为止
$ docker exec    # 在运行的容器中执行一条命令
```

（参考来源)[http://www.open-open.com/news/view/16e39b5/]