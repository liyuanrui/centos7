
### 1、下载mysql的repo包
```
http://dev.mysql.com/downloads/repo/yum/
```

### 2、卸载mariadb
```
rpm -qa | grep mariadb

rpm -e --nodeps mariadb-5.5.44-2.el7.centos.x86_64 mariadb-server-5.5.44-2.el7.centos.x86_64 mariadb-libs-5.5.44-2.el7.centos.x86_64 mariadb-devel-5.5.44-2.el7.centos.x86_64
```

### 3、安装下载的rpm包
```
rpm -ivh mysql57-community-release-el7-9.noarch.rpm
```

### 4、清理yum缓存和更新yun缓存
```
yum clean all
yum makecache
```

### 5、直接yum安装
```
yum install mysql-server
```

### 6、yum下载mysql
```
yum install mysql-server mysql-devel --downloadonly --downloaddir=/yum/
```
