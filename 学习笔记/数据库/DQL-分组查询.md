语法：
SELECT 字段列表 FROM 表名 \[WHERE 条件] GROUP BY 分组字段名 \[HAVING 分组后过滤条件]
演示：
![[Pasted image 20240505102714.png]]


注意：
- 和其他查询混用，比如和聚合函数混用
- **执行顺序：where>聚合函数>having**
- **分组之后，查询的字段一般为复合函数和分组字段，查询其他字段无任何意义**

where和having的区别
- 执行时机不同：where是分组之前进行过滤，不满足where条件，不参与分组；而having是分组之后对结果进行过滤
- 判断条件不同：where不能对聚合函数进行判断，而having可以