配置模块如何解析，创建import引入路径的别名，来确保模块引入变得更简单

例如：原来路径如图，比较长而且相对路径不安全

解决：在webpack.config.js中配置解析别名@来代表src绝对路径
![[Pasted image 20241031090835.png]]![[Pasted image 20241031090848.png]]