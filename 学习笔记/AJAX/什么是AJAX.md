![[Pasted image 20241012211723.png]]

#### 怎么使用AJAX
1.先使用axios库，与服务器进行数据通信
- 基于XMLHttpRequest封装，代码简单，月下载量在14亿次
- vue，React项目中都会用到axios
2再学习XMLHttpRequest对象的使用，了解AJAX底层原理



语法：
1.引用axios.js
2.使用axios函数
- 传入配置对象
- 再用.then回调函数接收结果，并做后续处理
![[Pasted image 20241012213002.png]]


需求：请求目标资源地址，拿到省份列表数据，显示到页面
目标资源地址：
![[Pasted image 20241012213202.png]]
```
    <div class="p"></div>

    <script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>

    <script>

        axios({url:'http://hmajax.itheima.net/api/province'}).then(result=>{

            console.log(result)

            console.log(result.data.list)

            document.querySelector('.p').innerHTML=result.data.list.join('<br>')

        })

    </script>
```