# 0. 前言 

要理解这么一个概念：

一个数据库中有多个表，一个表中可以存放多个数据。

所以前后关系：

- 数据库
- 表
- 数据

---

## 1. 查看数据库

首先入门的第一个命令是:

```sql
show databases;
```

**注意：每个语句写完后再写`;`**

然后是数据库的名。

|Databases|
|---|
|Information_scheme|
| anterbasea |
|mysql|
|performance_schema|
|sakila|
|sys|
|world|

这张样式表的话，可以看这么多数据库。

1. `Information_scheme`是基础数据信息，因为需要这个才能支持。
2. `mysql`是Mysql的配置数据库。
    * 密码
    * 用户名
    * 权限
3. `performace_scheme`数据库的运行数据；
    * 日志信息
    * 性能

---

## 2. 如何创建一个数据库？

```sql
    create database name;
```

上面是默认创建数据库。

但你可以不用默认的创建，也就是不写分号：

```sql
    create database name
```

将得到的是：

||
|---|

也可以定义字符集：

```sql
    default character set utf8 
```

定义utf-8的字符集。

特别要注意，在sql中是不支持-号，所以就写成uft8。

---

## 3. 删除数据库：

```sql
    drop database name;
```


## 2.1 创建表

```sql
    create table name(
```

表中的数据一个表示则是字段。

创建字段的名称的格式是：

|字段格式||
|---|:---|
|字段名称|字段类型|

如果有多个表的字段类型的话，就用逗号隔开。

```sql
    create table name(
        id int,
        name varchar(20)
    )
``

上面的`varchar`是指字段的符号，而一个符号必定要指定一个长度，那么20就是它长度。

完整的查看表名：

```sql
 desc [name]; 
```


| Field | Type        | Null | Key | Default | Extra |
|:---|:---|:---|:---|:---|:---|
| id    | int(11)     | YES  |     | NULL    |       |
| sname | varchar(20) | YES  |     | NULL    |       |



删除Table:

```sql
  drop [tablename]; 
```


如何新增表的字段呢？

```sql
create database student;
use student;
create table information(
    idName int,
    Name varchar(20)
);
alter table student add column sg varchar();
```

注意：column是指字段的意思。

更改数据类型：

```sql
alter table [tablename] modify [columnName] []
```

改数段名：

```sql
alter table [name] change [oldName] [newName] [type];
```

最后还是要将数据类型带入。
