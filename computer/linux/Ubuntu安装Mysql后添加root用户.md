# Ubuntu安装Mysql后添加root用户

1. 执行命令查看默认账户和密码

```sh
sudo cat /etc/mysql/debian.cnf
```

2. 使用查看到的账户和密码登入mysql

```mysql
mysql> mysql -u查看到的用户 -p
Enter password: 这里粘贴查看到的默认密码 然后回车
```

3. 然后执行下面的命令添加root用户

```mysql
mysql> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '123456';
mysql> quit;
```

