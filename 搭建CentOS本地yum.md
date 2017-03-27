
### 1、挂载镜像
```
mount CentOS-7-x86_64-Everything-1511.iso /mnt
```

### 2、修改CentOS-Sources.repo为CentOS-Local.repo
```
[Local]
name=Local Yum
baseurl=file:///mnt/
gpgcheck=1
enabled=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
```

### 3、清除yum缓存
```
yum clean all
```

### 4、生成缓存
```
yum makecache
```