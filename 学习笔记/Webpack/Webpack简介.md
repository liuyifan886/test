定义：本质上，webpack是一个用于现代JavaScript应用程序的静态模块打包工具，当webpack处理应用程序时，它会在内部从一个或多个入口点构建一个依赖图(dependency graph)，然后将你项目中所需的每一个模块组合成一个或多个bundles，他们均为静态资源，用于展示你的内容

静态模块：指的是编写代码过程中的，html，css，js，图片等固定内容的文件
打包：把静态模块内容，压缩，整合，转译等(前端工程化)
- 把less/sass转成css代码
- 把ES6+降级成ES5
- 支持多种模块标准语法



### Webpack使用方法
步骤
- 新建并初始化项目，编写业务源代码
- 下载webpack webpack-cil到当前项目中(版本独立)，并配置局部自定义命令 ![[Pasted image 20241028115952.png]] ![[Pasted image 20241028120008.png]]
- 运行打包命令，自动产生dist分发文件夹(压缩和优化后，用于最终运行的代码)![[Pasted image 20241028120025.png]]

运行流程图
![[Pasted image 20241028120049.png]]
