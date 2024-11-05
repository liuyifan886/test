概念：JDBC就是使用Java语言操作关系型数据库的一套API
全称：(Java database connectivity )Java数据库链接

JDBC本质上是一套接口，因为各种的数据库的操作不一样，所以它只是一个接口，实现类由别人完成
![[Pasted image 20240904225759.png]]

JDBC本质：
- 官方(sun公司)定义的一套操作所有关系型数据库的规则，即接口
- 各个数据库厂商去实现这套接口，提供数据库驱动jar包
- 我们可以使用这套接口(JDBC)编程，真正执行的代码是驱动jar包中的实现类，使用哪个数据库就使用哪个专属的jar包


JDBC好处：
- 各数据库厂商使用相同的接口，Java代码不需要针对不同数据库分别开发
- 可随时替换底层数据库，访问数据库的Java代码基本不变



#### JDBC快速入门
![[Pasted image 20240904231151.png]]


#### 如何添加jar包
new一个名字叫做lib的directory，并且把jar包放入lib里面
![[Pasted image 20240904231428.png]]
把jar包添加进library
![[Pasted image 20240904231546.png]]
弹出一个弹窗，project library，global library，module library分别代表全局有效，当前工程有效，模块有效
![[Pasted image 20240904231813.png]]


#### 连接实例
1.注册驱动(第一种方法已弃用)
![[Pasted image 20240905130429.png]]
![[Pasted image 20240905154807.png]]
2.获取连接
注：url是固定写法，用户名和密码是自己创建的
![[Pasted image 20240905130450.png]]
3.定义sql
![[Pasted image 20240905130636.png]]
4.获取执行sql的对象Statement
![[Pasted image 20240905130703.png]]
5.执行sql
![[Pasted image 20240905130725.png]]
6.处理结果
这个地方也是自己写的，想怎么处理靠自己
![[Pasted image 20240905130757.png]]
7.释放资源
![[Pasted image 20240905130839.png]]
