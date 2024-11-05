加载器css-loader：解析css代码
加载器style-loader：把解析后的css代码插入到DOM

步骤：
1.准备**css文件代码引入到src/login/index.js中**(压缩转译处理等)
2.下载css-loader和style-loader本地软件包
![[Pasted image 20241028214502.png]]
3.配置webpack.config.js让webpack拥有该加载器功能
![[Pasted image 20241028214518.png]]
4.打包后观察效果


#### 优化-提取css代码
好处：css文件可以被浏览器缓存；减少js文件体积
插件 mini-css-extract-plugin：提取css代码
步骤：
1.下载 mini-css-extract-plugin 本地软件包
![[Pasted image 20241028222535.png]]
2.配置 webpack.config.js让webpack拥有该插件功能
![[Pasted image 20241028222551.png]]
3.打包后观察效果

注意：不能和style-loader一起使用
好处：css文件可以被浏览器缓存，减少js文件体积

##### 优化-压缩过程
问题：css代码提取后没有被压缩
解决：使用css-minimizer-webpack-plugin插件
步骤：
1.下载css-minimizer-webpack-plugin本地软件包
![[Pasted image 20241029081515.png]]
2.配置webpack.config.js让webpack拥有该功能
它这个表示现在只能打包css文件，失去了打包js文件的能力，但是我们能根据作者的提示来恢复这个能力
![[Pasted image 20241029081529.png]]
3.重新打包观察