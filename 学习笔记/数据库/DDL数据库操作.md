### 查询
查询所有数据库
SHOW DATABASES;
查询当前数据库(在执行很多SQL语句后无法得知自己处在哪个数据库，就用该语句)
SELECT DATABASE();


### 创建
CREATE DATABASE \[IF NOT EXISTS] 数据库名 \[DEFAULT CHARSET 字符集] \[COLLATE 排序规则]
中括号里面的可省略，IF NOT EXISTS表示的是如果存在则不创建，不存在则创建



### 删除
DROP DATABASE 数据库名
如果在删除不存在的数据库时不想报错可以在数据库名前面加一个IF NOT EXISTS
数据库名记得加双引号


### 使用
USE 数据库名
