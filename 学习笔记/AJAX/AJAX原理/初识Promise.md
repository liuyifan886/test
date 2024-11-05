定义：Promise对象用于表示一个**异步操作完成(或失败)**及其结果值

学习的好处：
1.逻辑更清晰
2.了解axios函数内部运作机制
3.能解决回调函数地狱问题

语法：
![[Pasted image 20241017091340.png]]

代码演示
```
    <script>

        const p=new Promise((resolve,reject)=>{

            setTimeout(()=>{

            // resolve('认识成功')

            reject('认识失败')

        },1000)

        })
        //结果
        p.then(result=>{

            console.log(result)

        }).catch(error=>{

            console.log(error)

        })

    </script>
```