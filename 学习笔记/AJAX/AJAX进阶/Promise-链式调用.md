概念：依靠then()方法会返回一个新生成的Promise对象特性，继续串联下一环任务，直到结束
细节：then()回调函数中的返回值，会影响新生成的Promise最终状态和结果
好处：通过链式调用，解决回调函数嵌套问题

![[Pasted image 20241018103141.png]]```
  <script>

    /**

     * 目标：掌握Promise的链式调用

     * 需求：把省市的嵌套结构，改成链式调用的线性结构

    */

    const p=new Promise((resolve,reject)=>{

        setTimeout(()=>{

            resolve('北京市')

        },2000)

    })

    const p2=p.then(result=>{

        console.log('你好')

        return new Promise((resolve,reject)=>{

            setTimeout(() => {

                resolve(result+'---北京')

            }, 2000)

        })

    })

    p2.then(result=>{

        console.log(result)

    })

  </script>
```
```
#### 解决回调函数地狱问题
```
  <script>

    /**

     * 目标：把回调函数嵌套代码，改成Promise链式调用结构

     * 需求：获取默认第一个省，第一个市，第一个地区并展示在下拉菜单中

    */

   let provinceValue=''

    axios({

      url:'http://hmajax.itheima.net/api/province'

    }).then(result=>{

      const provinceStr=result.data.list.map(item=>

        `<option>${item}</option>`

      ).join('')

      document.querySelector('.province').innerHTML=provinceStr

      provinceValue=document.querySelector('.province').value

      return axios({

        url:'http://hmajax.itheima.net/api/city',

        params:{

          pname:provinceValue

        }

      })

    }).then(result=>{

      document.querySelector('.city').innerHTML=result.data.list[0]

      return axios({

        url:'http://hmajax.itheima.net/api/area',

        params:{

          pname:provinceValue,

          cname:result.data.list[0]

        }

      })

    }).then(result=>{

      document.querySelector('.area').innerHTML=result.data.list[0]

    })
```