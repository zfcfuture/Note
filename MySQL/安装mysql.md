### 安装mysql

不同系统下安装mysql数据库的方式也有所区别

#### 1.  Ubuntu20

```shell
# 1.切换到root用户下
su root

# 2.安装
sudo apt update
sudo apt install mysql-server

# 3.安装完后可以查看mysql版本
mysql -V

# 4.登录mysql（第一次密码为空）
mysql -uroot -proot

# 5.修改密码
mysql> use mysql;
mysql> CREATE USER 'root'@'%' IDENTIFIED BY '要设置的密码';
mysql> flush privileges;

# 6.设置远程登录
vim /etc/mysql/mysql.conf.d/mysqld.cnf
#bind-address            = 127.0.0.1
bind-address            = 0.0.0.0

# 7.重启mysql服务
service mysql restart

# Note: 如果使用的是云服务器(阿里云，腾讯云)，记得去安全组查看3306端口是否开放
```

