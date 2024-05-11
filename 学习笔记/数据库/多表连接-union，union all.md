对于union查询，就是把多次查询的结果合并起来，形成一个新的查询结果集

SELECT 字段列表 FROM 表A...WHERE 条件
UNION \[ALL]
SELECT 字段列表 FROM 表B...WHERE 条件


- 如果出现重复的结果，把ALL去掉就没有重复的查询结果了
- 对于联合查询的多张表的列数必须保持一致，字段类型也需要保持一致
- union all会将全部的数据直接合并在一起，union会对合并之后的数据去重

