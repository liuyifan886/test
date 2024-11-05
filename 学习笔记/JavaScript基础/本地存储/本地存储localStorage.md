能够使用localStorage把数据存储到浏览器中
作用：可以将数据==永久存储在本地(==用户的电脑)，除非手动删除，否则关闭页面也会存在,但是跨域不能共享，比如淘宝和京东肯定不能共享
特性：
可以多窗口(页面)共享(同一浏览器可以共享)
以键值对的形式储存使用



语法：
存储数据：
localStorage.setItem(key,value)
获取数据：
localStorage.getItem(key,value)
删除数据：
localStorage.removeItem(key)

![[Pasted image 20240910225656.png]]