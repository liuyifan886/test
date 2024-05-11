DELETE FROM 表名 \[where 条件]


#### 注意
- delete语句的条件可以有，也可以没有，如果没有条件，则会删除整张表的所有数据
- delete语句不能删除某一个字段的值(可以使用update，就是把字段值改成null)
