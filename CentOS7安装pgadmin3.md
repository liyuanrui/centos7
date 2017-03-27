
### 1、下载repo包
```
wget http://ftp.riken.jp/Linux/centos/7/extras/x86_64/Packages/epel-release-7-6.noarch.rpm
```

### 2、清除缓存和更新缓存
```
yum clean all
yum makecache
```

### 3、下载安装rpm包
```
yum install pgadmin3 --downloadonly --downloaddir=/yum
```
