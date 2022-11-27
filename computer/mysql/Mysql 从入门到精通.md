# Mysql日常操作笔记

命令行下连接mysql数据库

```mysql
mysql -h127.0.0.1 -P3306 -uroot -proot
```

> 如果是连接本地数据库， -h可以省略 如果服务器端口是3306，-P端口号也可以省略



退出登入命令

```mysql
exit 或者 \q
```



显示数据库列表，记得要有分号结尾

```mysql
show databases;
```



创建数据库命令

```mysql
create database stu;
create database if not exists stu;  # 判断数据库是否存在，不存在则创建
```

特殊字符或者关键字做数据库名，使用反引号将数据库名括起来

```mysql
create database `create`;
create database `%$`;
```

创建数据库指定字符编码

```mysql
create database test charset=gbk;
```



删除数据库命令

```mysql
drop database test;
```

删除特殊字符的数据库

```mysql
drop database `create`;
```

判断数据库是否存在，存在则删除

```mysql
drop database if exists test;
```



修改数据库字符编码

```mysql
alter database test charset=utf8;
```



选择数据库命令

```mysql
use test;
```



查看有哪些表

```
show tables;
```

设置客户端和服务器通讯的编码，不设置不能使用中文

```
set names gbk;
```

