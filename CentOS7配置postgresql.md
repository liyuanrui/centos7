
### 1、初始化postgresql并启动和加入开机自启
```
postgresql-setup initdb
如若初始化不了，那就全都删了less /var/lib/pgsql/data/*
systemctl restart postgresql
systemctl enable postgresql
chkconfig --level 345 postgresql on
```

### 2、切换用户修改密码
```
# su postgres
bash-4.2$ psql
postgres=# \password postgres
```

### 3、修改认证文件/var/lib/pgsql/data/pg_hba.conf，登陆使用密码
把这个配置文件中的认证 METHOD的ident修改为trust，可以实现用账户和密码来访问数据库，
即解决psql: 致命错误: 用户 "postgres" Ident 认证失败 这个问题）
```
vim /var/lib/pgsql/data/pg_hba.conf
local all all              trust
host  all all 127.0.0.1/32 trust
host  all all ::3/128      trust
```

### 4、配置全局监听
修改配置文件/var/lib/pgsql/data/postgresql.conf
```
确认以下内容：
listen_addresses = '*' 
port=5432            
修改认证文件/var/lib/pgsql/data/pg_hba.conf
确认以下内容：
host    all             all             all            md5
```

### 5、重启postgresql服务器使设置生效
```
systemctl restart postgresql.service
```
