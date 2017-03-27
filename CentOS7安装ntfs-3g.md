
### 1、加源
```
wget -O /etc/yum.repos.d/epel.repo http://mirrors.aliyun.com/repo/epel-7.repo
```

### 2、下载
```
yum clean all
yum makecache
yum install ntfs-3g --downloadonly --downloaddir=/yum
```

### 3、安装
```
rpm -ivh ntfs-3g-2016.2.22-1.el7.x86_64.rpm
```
