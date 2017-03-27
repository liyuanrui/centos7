
### 1、安装开发工具
```
yum groupinstall "Development Tools" -y
```

### 2、更新yum
```
yum update
```

### 3、移除audit
```
yum remove audit
```

### 4、安装依赖
```
yum install -y python-devel openssl-devel libxslt-devel libxml2-devel
```

### 5、安装pip和easy_install
```
wget https://bootstrap.pypa.io/get-pip.py
python get-pip.py
```

### 6、安装lxml
```
easy_install lxml
```

### 7、安装scrapy
```
pip install scrapy
```
