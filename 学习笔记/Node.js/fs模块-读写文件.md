模块：类似插件，封装了方法/属性
fs模块：封装了与本机文件系统进行交互的方法或属性
语法；
1.加载fs模块对象
![[Pasted image 20241025091751.png]]
2.写入文件内容
![[Pasted image 20241025091802.png]]
3.读取文件内容
![[Pasted image 20241025091816.png]]

代码演示
```
//加载js模块对象

const fs=require('fs')

  

//写入文件内容

fs.writeFile('./test.txt','Hello Node.js',err=>{

    if(err){

        console.log(err)

    }else{

        console.log('写入成功')

    }

}

)

//读取文件内容

fs.readFile('./test.txt',(err,data)=>{

    if(err){

        console.log(err)

    }else{

        console.log(data.toString())

    }

})
```