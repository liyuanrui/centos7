
### 1、首先试试服务器装了VNC没
```
rpm -q tigervnc tigervnc-server
```

### 2、安装VNC packages
```
yum install tigervnc-server -y
```

### 3、修改配置信息
在/etc/systemd/system/下建立文件夹vncserver@:1.service 把example config 文件从/lib/systemd/system/vncserver@.service复制到里面
```
cp /lib/systemd/system/vncserver@.service /etc/systemd/system/vncserver@:1.service
```

### 4、替换掉默认用户名
打开这个配置文件/etc/systemd/system/vncserver@:1.service替换掉默认用户名
```
vim /etc/systemd/system/vncserver@:1.service

ExecStart=/sbin/runuser -l <USER> -c "/usr/bin/vncserver %i"
PIDFile=/home/<USER>/.vnc/%H%i.pid
替换<USER>
ExecStart=/sbin/runuser -l root -c "/usr/bin/vncserver %i"
PIDFile=/root/.vnc/%H%i.pid
```

### 5、重加载 systemd
```
systemctl daemon-reload
```

### 6、为VNC设密码
```
vncpasswd
```

### 7、启动vnc
```
systemctl enable vncserver@:1.service
systemctl start vncserver@:1.service
```

### 8、vnc报错起不来
```
rm -rf /tmp/.X11-unix/*
```

### 9、vnc常用命令
```
vncserver            #start vncserver,default :1
vncserver -list      #show the running process with vncserver
vncserver -kill :1   #kill the vncserver process by display number
vncserver :2         #start vncserver,display number is :2

```

### 10、指定分辨率
```
vncserver -geometry 1366x786
```
