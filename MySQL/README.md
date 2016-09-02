# MySQL

## start / restart / stop
```
# /usr/sbin/mysqld start/restart/stop 
```
> can not execute under root


```
# /user/sbin/mysqld --user=root start # force
```
> cause error
> `InnoDB: Unable to lock ./ibdata1, error: 11`

> cause:
> - storage not enough
> - memory not enough

```
# service mysqld start
```
> This way will success



## `GRANT` privileges

```shell
$ mysql -u root -h localhost -p

mysql> select host,user,password from mysql.user;

mysql> show grants fro 'root'@'127.0.0.1';

mysql> select user();         # what you attempted to login as
mysql> select current_user(); # what you actually connected as

mysql> update mysql.user set grant_priv='Y', super_priv='Y' where user='root';
msyql> flush privileges;
mysql> grant all on *.* to 'root'@'127.0.0.1' identified by 'pwd';

mysql> SELECT * FROM mysql.user WHERE User='root' \G

mysql> exit

$ /usr/sbin/mysql restart     # 测试中，只有重启后才生效，`flush privileges;` 好像并没有起作用
# 上述重启方法，在root帐号下，是不起作用的
```


