定义：浏览器提供给服务器的额外信息，让服务器返回浏览器想要的数据
需要自己在后面拼接
![[Pasted image 20241015151803.png]]
![[Pasted image 20241015151736.png]]

```
<body>

    <p class="my-p"></p>

  <script>

    /**

     * 目标：使用XHR携带查询参数，展示某个省下属的城市列表

    */

    const xhr=new XMLHttpRequest()

    xhr.open('get','http://hmajax.itheima.net/api/city?pname=辽宁省')

    xhr.addEventListener('loadend',()=>{

        const data=JSON.parse(xhr.response).list

        document.querySelector('.my-p').innerHTML=data.join('<br>')

    })

    xhr.send()

  </script>

</body>
```

如果请求的参数有很多，有另外一个方法
![[Pasted image 20241016080309.png]]