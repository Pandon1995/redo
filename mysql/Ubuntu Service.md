# Ubuntu Service下启动MySQL数据库的三种方式

## 说明

1. 系统环境：ubuntu service 12.10 x64（mysql为系统自带）

2. 在windows系统下，mysql的配置文件为my.ini，在linux系统下，mysql的配置文件为my.cnf，并且my.cnf文件位置为：/ect/mysql/my.cnf
可以根据自己的需求，用gedit修改mysql的配置文件（my.cnf）：sudo gedit /etc/mysql/my.cnf

3. Waring：如果该配置文件错误，MySQL将无法启动

## 启动mysql

### 方式一

sudo /etc/init.d/mysql start

### 方式二

sudo start mysql

### 方式三

sudo service mysql start

## 停止mysql

### 方式一

sudo /etc/init.d/mysql stop

### 方式二

sudo stop mysql

### 方式三

sudo service mysql stop

## 重启sql

### 方式一

sudo /etc/init.d/mysql restart

### 方式二

sudo restart mysql

### 方式三

sudo service mysql restart

#  在Ubuntu上在线安装Mysql

## 安装 mysql 服务端、核心程序

sudo apt-get install mysql-server

## 安装 mysql 客户端

sudo apt-get install mysql-client

## 验证是否安装并启动成功

sudo netstat -tap | grep mysql

# mysql基本命令

## 打开mysql

1. 启动mysql服务：sudo service mysql start
2. 使用root用户登录，当密码为空时：mysql -u root

## 新建数据库和连接数据库

create database <数据库名>；
use <数据库名>；

## 查看表、新建表、删除表

数据表（table）简称表，它是数据库最重要的组成部分之一，数据库只是一个框架，表才是实质内容。一个数据库中一般会有多张表，这些表通过建立关系被连接起来。
show tables；

create table <表的名字>（列名a 数据类型(数据长度)，列名b 数据类型(数据长度)，列名c 数据类型(数据长度)，）；

drop table <表名>；

## 插入数据

1. 新建表之后，查看表中的数据：
语句格式：select * from <表名>；
2. 通过insert语句向表中插入数据：
语句格式：insert into <表的名字>(列名a,列名b，列名c) values(值1，值2，值3)；
3. 举例：向employee表中加入Tom、Jack和Rose：
insert into employee(id,name,phone) values(01,'Tom',110110110);

insert into employee values(02,'Jack',119119119);

insert into employee(id,name) values(03,'Rose');
4. 说明：有的数据需要单括号括起来，比如Tom等名字，这是因为这些数据类型是char型，此外varchar,text,date,time,enum也需要单引号修饰，而int,float,double 等就不需要。

## 查看和删除数据库

show databases；
drop database <数据库名>；






