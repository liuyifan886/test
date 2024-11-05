定义：CommonJS模块是为Node.js打包JavaScript代码的原始方式，Node.js还支持浏览器和其他JavaScript运行时使用的ECMAScript模块标准，在Node.js，每个文件都被视为一个单独的模块

概念：项目是由很多个模块文件组成的
好处：提高代码复用性，按需加载，独立作用域
使用：需要标准语法导出和导入进行使用


##### CommonJS标准
![[Pasted image 20241027080703.png]]
对外属性名是外界调用时的名字

使用：
1.导出：module.exports={}
2.导出：require(‘模块或路径’)

模块或路径：
内置模块：直接写名字(例如：fs，path，http)
自定义模块：写模块文件路径(例如：./utils.js)
