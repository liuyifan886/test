Node.js代码中，相对路径是根据终端所在路径来查找的，可能无法找到你想要的文件
建议：在Node.js代码中，使用绝对路径
补充：\_\_dirname内置变量(注意前面是两个下划线)(获取当前模块目录-绝对路径)

mac系统和window系统的文件路径间隔符不同
![[Pasted image 20241025100456.png]]
为了让咱的代码通用：
path.join()会使用特定于平台的分隔符，作为定界符，将所有给定的路径片段连接在一起
语法：
1.加载path模块
![[Pasted image 20241025100857.png]]
2.使用path.join方法，拼接路径
![[Pasted image 20241025100906.png]]

代码演示
```
//引入fs模块

const fs=require('fs')

//引入path模块

const path=require('path')

console.log(__dirname)

fs.readFile(path.join(__dirname,'../test.txt'),(err,data)=>{

    if(err){

        console.log(err)

    }else{

        console.log(data.toString())

    }

})
```