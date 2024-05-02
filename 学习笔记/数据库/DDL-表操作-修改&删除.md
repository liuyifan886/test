**添加字段**
ALTER TABLE 表名 ADD 字段名 类型(长度)\[COMMENT注释] \[约束]
例子，为表添加一个新的字段“昵称”为nickname，类型为varchar(20)

**修改数据类型**
ALTER TABLE 表名 MODIFY字段名 新数据类型(长度)；

**修改字段名和字段类型**
ALTER TABLE 表名 CHANGE 旧字段名 新字段名 类型(长度) \[COMMENT‘注释’]；
例子：
![[Pasted image 20240502153632.png]]
  **删除字段**
  ALTER TABLE 表名 DROP 字段名;


**修改表名**
ALTER TABLE 表名 RENAME TO 新表名;
![[Pasted image 20240502154256.png]]


### 删除表
DROP TABLE \[IF EXISTS] 表名;
if exists 还是有就执行没有也不报错


### 删除指定表，并重新创建该表
TRUNCATE TABLE 表名;
通俗话来讲就是格式化该表数据，但是表结构还在