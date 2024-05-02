### List集合的特点
- 有序：存和取的元素顺序一致
- 有索引：可以通过索引操作角色
- 可重复：存储的元素可以重复

### List集合的特有方法
Collection的方法List都继承了
List集合因为有索引，所以多了很多索引操作的方法
![[Pasted image 20240425223352.png]]
add方法细节：把指定元素放在指定索引上，原来索引上的元素和之后的会往后移
remove方法细节：
![[Pasted image 20240425224557.png]]
set方法没什么好说的，修改元素并返回之前的那个元素
get方法得到指定索引的元素



### List集合的遍历方法
- 迭代器，为继承Collection的方法，详情在[[Collection的遍历方式]]
- 增强for，也是继承Collection的方法，详情在[[Collection的遍历方式]]
- Lambda，继承Collection的方法，详情在[[Collection的遍历方式]]
- 普通for循环，利用索引，get来获得并遍历
- 列表迭代器，List独有，是一个接口Listiterator的方法，看起来似乎和迭代器没区别？新添了一个添加元素的方法
- ![[Pasted image 20240426232017.png]]


### 各种遍历方法的使用时机
![[Pasted image 20240426232156.png]]

