location的数据类型是对象，它拆分并保存了**URL地址的各个组成成分**
常用属性和方法
href属性获取完整的URL地址，对其赋值时用于地址的跳转，运行会直接跳转
![[Pasted image 20240830165936.png]]
search属性获取地址中携带的参数，符号？后面部分
![[Pasted image 20240830180503.png]]
![[Pasted image 20240830180517.png]]
hash属性获取地址中的哈希值
后期vue路由的铺路，经常用于不刷新页面，显示不同页面，比如网易云音乐
![[Pasted image 20240830181558.png]]
![[Pasted image 20240830181624.png]]
reload方法用来刷新当前页面，传入参数true时表示强制刷新
![[Pasted image 20240830181723.png]]
