首先是编写顺序：(编写顺序和执行顺序不一样)
SELECT 字段列表
FROM 表名列表
WHERE 条件列表
GROUP BY 分组字段列表
HAVING 分组后条件列表
ORDER BY 排序字段列表
LIMIT 分页参数

执行顺序：
FROM  表名列表(查找对应的表)
WHERE 条件列表(筛选符合条件的)
GROUP BY 分组字段列表(把符合条件的分组)
HAVING 分组后条件列表(第二次筛选)
SELECT 字段列表 (选择把字段显示出来)
ORDER BY 排序字段列表 (排序)
LIMIT 分页参数 (分页选择展示的参数)