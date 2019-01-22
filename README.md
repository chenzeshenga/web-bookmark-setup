# web-bookmark

https://segmentfault.com/a/1190000010756385

activiti的缓存(redis)(https://www.cnblogs.com/core404/p/7550519.html)

# redis setup 
  ## use the msi file in baidu cloud disc & click next till end
  
# mongodb setup
  ## use the msi file in baidu cloud disc & click next till end

https://blog.csdn.net/caicongyang/article/details/50650136

https://blog.csdn.net/liuchuanhong1/article/details/70147149

https://www.webpackjs.com/

https://www.npmjs.cn/all/

https://blog.csdn.net/legend11/article/details/53408459 javacript onclick事件中传递对象参数

----

ubuntu 安装maven

sudo apt-get install maven

----

ubuntu 默认配置安装redis

sudo apt-get install redis-server

安装完成后redis 已自动加入开机启动项,可在/etc/init.d目录下查看

查看进程
ls -ltr |grep redis

启动/停止/查看 redis服务
systemctl start/stop/status redis

----

ubuntu 默认配置安装mysql

```sql
sudo apt-get install mysql-server

# 启动/停止/重启/查看mysql服务
service mysql start/stop/restart/status
systemctl start/stop/restart/status mysql

# 查看默认安装密码
cat /etc/mysql/debian.cnf

# 创建用户并允许远程/本地登录
grant all privileges on *.* to 'root'@'%' identified by 'yourpassword' with grant option;
flush privileges;
# 查看用户拥有的权限
show grants for root;
# 修改认证方式
select user,plugin from user;
# 如果plugin为auth_socket,需要修改为'mysql_native_password'
update user set authentication_string=password('yourpassword'),plugin='mysql_native_password' where user='root';
flush privileges;
# 取消地址绑定
vi /etc/mysql/mysql.conf.d/mysqld.cnf
# 注释掉bind的一行,并重启服务
# 查看是否开机启动
ls -l /etc/init.d |grep mysql
```

----

ubuntu 默认安装配置最新版rabbitmq

```bash
wget -O - 'https://dl.bintray.com/rabbitmq/Keys/rabbitmq-release-signing-key.asc' | sudo apt-key add -

echo "deb https://dl.bintray.com/rabbitmq/debian bionic main erlang" | sudo tee /etc/apt/sources.list.d/bintray.rabbitmq.list

sudo apt-get update

# 卸载之前安装的rabbitmq和erlang
sudo apt-get remove rabbitmq
sudo apt-get purge erlang
sudo apt-get autoremove

sudo apt-get install erlang
sudo apt-get install rabbitmq-server

# 启动/停止/查看 rabbitmq 服务
sudo rabbitmqctl start_app/stop_app/status

# 查看是否开机启动
ls -ltr /etc/init.d/ |grep rabbitmq

# 安装管理页面插件
sudo rabbitmq-plugins enable rabbitmq_management

# 查看用户列表
sudo rabbitmqctl list_users

# 新增管理员用户
sudo rabbitmqctl add_user admin admin 
sudo rabbitmqctl set_user_tags admin administrator
```

----
ubuntu 安装nodejs

```bash
sudo apt-get install curl
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt-get install nodejs
```

----
ubuntu 安装mongodb
```bash
sudo apt-get install mongodb
systemctl status/stop/start mongodb

```
