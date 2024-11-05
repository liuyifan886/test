定义：async函数是使用async关键字声明的函数，async函数是AsyncFunction构造函数的实例，并且其中允许使用await关键字，async和await关键字让我们可以用一种更简洁的方式写出基于Promise的异步行为，而无需刻意的调用promise

概念：在async函数内，使用await关键字取代then函数，等待获取Promise对象成功状态的结果值
![[Pasted image 20241019101410.png]]


代码演示
```
  <script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>

  <script>

    /**

     * 目标：掌握async和await语法，解决回调函数地狱

     * 概念：在async函数内，使用await关键字，获取Promise对象"成功状态"结果值

     * 注意：await必须用在async修饰的函数内（await会阻止"异步函数内"代码继续执行，原地等待结果）

    */

   async function getData(){

    const pObj=await axios({url:'http://hmajax.itheima.net/api/province'})

    const pname=pObj.data.list[0]

    const cObj=await axios({url:'http://hmajax.itheima.net/api/city',params:{pname}})

    const cname=cObj.data.list[0]

    const aObj=await axios({url:'http://hmajax.itheima.net/api/area',params:{pname,cname}})

    const aname=aObj.data.list[0]

  

    document.querySelector('.province').innerHTML=pname

    document.querySelector('.city').innerHTML=cname

    document.querySelector('.area').innerHTML=aname

   }

   getData()

  </script>
```