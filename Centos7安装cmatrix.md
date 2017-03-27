
### 1、安装依赖
```
yum install gcc make autoconf automake ncurses-devel
```

### 2、下载
```
wget http://www.asty.org/cmatrix/dist/cmatrix-1.2a.tar.gz  
```

### 3、解压进入
```
tar xzvf cmatrix-1.2a.tar.gz  
cd cmatrix-1.2a  
```

### 4、编译安装
```
aclocal  
autoconf 
automake -a   
./configure 
make  
make install
```
