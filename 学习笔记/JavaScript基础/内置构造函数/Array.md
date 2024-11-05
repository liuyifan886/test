是内置都构造函数，用于创建数组
![[Pasted image 20240928111212.png]]

创建数组建议使用字面量创建，不用Array构造函数创建


一些常用函数
reduce 返回累计处理的结果，经常用于求和等
基本语法
上一次值，当前值和初始值用想要的变量名进行设置即可
![[Pasted image 20240928111702.png]]![[Pasted image 20240928111735.png]]
![[Pasted image 20240928111746.png]]
具体写法
```
        const arr=[1,2,3,5]

        const total=arr.reduce(function(prve,current){

            return prve+current

        },10)

        console.log(total)
        //箭头函数写法
        const total=arr.reduce((prve,current)=>prve+current,10)

        console.log(total)
```

执行流程
1.如果没有起始值，则==上一次值以数组的第一个数组元素的值==
2.每一次循环，把返回值给做为下一次循环的上一次值
3.如果有起始值，则起始值作为上一次值


数组常见方法
![[Pasted image 20240928162849.png]]

find方法
这个方法适合与找某个对象，而filter返回数组适合找很多个对象
![[Pasted image 20240928162919.png]]、
every方法
![[Pasted image 20240928163642.png]]


伪数组转换成真数组
静态方法Array.from()
![[Pasted image 20240928164645.png]]