
### 1、关闭防火墙
```
systemctl stop firewalld
systemctl disable firewalld
systemctl status firewalld
```

### 2、关闭SELINUX
```
vim /etc/selinux/config
SELINUX=disabled
```