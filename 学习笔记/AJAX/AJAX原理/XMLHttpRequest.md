定义：XMLHttpRequest(XHR)对象用于与服务器交互，通过XMLHttpRequest可以在不刷新页面的情况下请求特定URL，获取数据，这允许网页在不影响用户操作的情况下，更新页面的局部内容，XMLHttpRequest在AJAX编程中被大量使用
关系：axios内部采用XMLHttpRequest与服务器交互
![[Pasted image 20241015145214.png]]

好处：掌握使用XHR与服务器进行数据交互，了解axios内部原理


#### 使用XMLHttpRequest
步骤：
1.创建XMLHttpRequest(对象
2.配置请求方法和请求url地址
3.监听loadend事件，接受响应结果
4.发起请求
![[Pasted image 20241015145626.png]]

```
<body>

    <p class="my-p"></p>

  <script>

    /**

     * 目标：使用XMLHttpRequest对象与服务器通信

     *  1. 创建 XMLHttpRequest 对象

     *  2. 配置请求方法和请求 url 地址

     *  3. 监听 loadend 事件，接收响应结果

     *  4. 发起请求

    */

  

    const xhr=new XMLHttpRequest()

    xhr.open('GET','http://hmajax.itheima.net/api/province')

    xhr.addEventListener('loadend',()=>{

        console.log(xhr.response)

        const data=JSON.parse(xhr.response)

        console.log(data.list)

        document.querySelector('.my-p').innerHTML=data.list.join('<br>')

    })

    xhr.send()

  </script>

</body>
```


#### XMLHttpRequest-查询参数
定义：浏览器提供给服务器的额外信息，让服务器返回浏览器想要的数据