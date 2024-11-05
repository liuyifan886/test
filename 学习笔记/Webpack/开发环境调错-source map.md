问题：代码被压缩和混淆，无法正确定位源代码位置(行数和列数)

source map：可以准确追踪error和warning在原始代码的位置

设置：webpack.config.js配置devtool 选项

![[Pasted image 20241031084613.png]]

inline-source-map选项：把源码的位置信息一起打包在.js文件内
注意：source map仅适用于开发环境，不要在生产环境使用(防止被轻易查看源码位置)

通过配置环境变量来区分其在哪个模式,
![[Pasted image 20241031085239.png]]