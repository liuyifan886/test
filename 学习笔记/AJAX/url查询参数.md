定义：浏览器提供给服务器的额外信息，让服务器返回浏览器想要的数据
语法：http://xxxx.com/xxx/xxx?参数名=值1&参数名2=值2
![[Pasted image 20241012220402.png]]

语法：使用axios提供的params选项
注意：axios在运行时把参数名和值，会拼接到url?参数名=值
![[Pasted image 20241012220628.png]]

代码演示：
```
    <script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>

    <script>

        axios({

            url:'http://hmajax.itheima.net/api/city',

            params:{

                pname:'辽宁省'

            }

        }).then(result=>{

            console.log(result.data.list)

        })

    </script>
```