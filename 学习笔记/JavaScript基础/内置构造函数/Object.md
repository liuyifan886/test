是内置的构造函数，用于创建普通对象
![[Pasted image 20240928105500.png]]
推荐使用字面量方式声明对象，而不是Object构造函数

三个常用静态方法，只有Object对象能够调用 
作用：Object.keys 静态方法获取对象中所有属性键
语法：
![[Pasted image 20240928110300.png]]
注意：返回的是一个数组


作用Object.values静态方法获取对象中所有属性值
语法：
![[Pasted image 20240928111110.png]]
注意：返回的是一个数组

作用：Object.assign静态方法常用于对象拷贝
使用：经常使用的场景==给对象添加属性==
![[Pasted image 20240928110740.png]]