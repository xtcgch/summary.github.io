#常用SQL原生语句

[TOC]

---


## 数据库
- 创建数据库

```
CREATE DATABASE if not exists database-name
```

- 删除数据库

```
drop database dbname
```

## 表
- 创建表

```
create table if not exists usertable(_id integer primary key autoincrement,sname text,snumber text）
```

- 删除新表

　
```
drop table tabname
```

##增加一个列

```
Alter table tabname add column col type
```

##添加主键
 
```
Alter table tabname add primary key(col)
```

##索引
- 创建索引

```
create [unique] index idxname on tabname(col….)
```

- 删除索引

```
drop index idxname
```

##视图
- 创建视图：

```
 create view viewname as select statement
```

- 删除视图：

```
drop view viewname
```

##CRUD增删改查
- 选择：

```
select * from table1 where 范围
```

- 插入：

```
insert into table1(field1,field2) values(value1,value2)
```
- 删除：

```
delete from table1 where 范围
```

- 更新：

```
update table1 set field1=value1 where 范围
```

- 查找：

```
select * from table1 where field1 like ’%value1%’
```

- 排序：

```
select * from table1 order by field1,field2 [desc]
```
- 总数：

```
select count as totalcount from table1
```
- 求和：

```
select sum(field1) as sumvalue from table1
```
- 平均：

```
select avg(field1) as avgvalue from table1
```
- 最大：

```
select max(field1) as maxvalue from table1
```
- 最小：

```
select min(field1) as minvalue from table1
```

##高级查询
-  UNION 运算符
-  EXCEPT 运算符
-  INTERSECT 运算符
-  join 运算符
-  分组:Group by
-  子查询(表名1：a 表名2：b)

```
select a,b,c from a where a IN (select d from b ) 或者: select a,b,c from a where a IN (1,2,3)
```

-  显示文章、提交人和最后回复时间

```
select a.title,a.username,b.adddate from table a,(select max(adddate) adddate from table where table.title=a.title) b
```

- between
```
select * from table1 where time between time1 and time2

select a,b,c, from table1 where a not between 数值1 and 数值2
```

- in 的使用方法

```
select * from table1 where a [not] in (‘值1’,’值2’,’值4’,’值6’)
```
- 日程安排提前五分钟提醒

```
select * from 日程安排 where datediff('minute',f开始时间,getdate())>5
```
- 数据库分页

```
select top 10 b.* from (select top 20 主键字段,排序字段 from 表名 order by 排序字段 desc) a,表名 b where b.主键字段 = a.主键字段 order by a.排序字段
```
- 前10条记录

```
select top 10 * form table1 where 范围
```
- 选择从10到15的记录

```
select top 5 * from (select top 15 * from table order by id asc) table_别名 order by id desc
```
