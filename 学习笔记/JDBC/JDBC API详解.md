#### DriverManager(驱动管理类)作用：
##### 1.注册驱动
![[Pasted image 20240905221315.png]]
源码
![[Pasted image 20240905221330.png]]
提示：
1.MySQL5之后的驱动包，可以省略注册驱动的步骤
2.自动加载jar包中META-INF/services/java.sql.Driver文件中的驱动类

##### 2.获取数据库连接
获取连接
![[Pasted image 20240905222043.png]]

参数
1.url：连接路径
![[Pasted image 20240905222123.png]]
2.user：用户名
3.password：密码


#### Connection
作用
##### 1.获取执行SQL的对象(前面的单词为返回的对象)
- 管理执行SQL对象
- ![[Pasted image 20240905223004.png]]
- 预编译SQL的执行对象：防止SQL注入
- ![[Pasted image 20240905223037.png]]
- 执行储存过程的对象
- ![[Pasted image 20240905223059.png]]

##### 2.管理事务
MySQL事务管理
![[Pasted image 20240905223539.png]]

JDBC事务管理：Connection接口中定义了三个对应的方法
![[Pasted image 20240905223616.png]]
利用try...catch来进行事务的处理，先开启手动提交事务，若事务有异常就回滚


#### Statement
作用：执行SQL语句
[[SQL使用方法及分类]]
![[Pasted image 20240905224720.png]]
执行DML语句可以靠返回值来判断(判断是否大于0)是否执行成功，但是DDL不行

![[Pasted image 20240905224900.png]]


#### ResultSet
结果集对象
封装了DQL查询语句的结果
![[Pasted image 20240906094042.png]]

##### 获取查询结果
![[Pasted image 20240906094353.png]]
![[Pasted image 20240906094410.png]]

##### 获取数据步骤
1.游标向下移动一行，并判断该行是否有数据：next()
2.获取数据：getXxx(参数)
![[Pasted image 20240906094854.png]]

图例
![[Pasted image 20240906095712.png]]
![[Pasted image 20240906095849.png]]
使用方法：查询数据，然后获取并把数据封装到对象里，储存到ArrayList里面，方便展示