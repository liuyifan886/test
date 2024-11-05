vue会根据不同的指令，针对标签实现不同的功能
指令：带有v- 前缀的特殊标签属性
![[Pasted image 20241103230113.png]]v-html
作用：设置元素的innerHTML
表达：v-html="表达式"

v-show
作用：控制元素显示隐藏
语法：v-show=“表达式”，表达式值true显示，false隐藏
底层原理：切换css的display：none来控制显示隐藏
使用场景：频繁切换显示隐藏的场景

v-if
作用：控制元素显示隐藏(条件渲染)
语法：v-if=“表达式”  表达式值true显示，false隐藏
底层原理：根据判断条件控制元素的创建和移除(条件渲染)
使用场景：要么显示要么隐藏，不频繁切换的场景

v-else和v-else-if
作用辅助v-if进行判断渲染
语法：v-else v-else-if=“表达式”
注意：需要紧挨着v-if一起使用


用法截图
![[Pasted image 20241104081551.png]]

# v-on
作用：注册事件=添加监听+提供处理逻辑 
语法：
- v-on:事件名=“内联语句” (内联语句是写在此处的函数)
- v-on:事件名=“methods中的函数名“ (这个是在外面写好，放函数名在这里被调用)

内联样式写法
一直写v-on：会很麻烦，所以可以把他替换成@
![[Pasted image 20241104082732.png]]


methods写法
![[Pasted image 20241104114933.png]]
注：methods函数内的this指向vue案例，所以可通过这个来获取数据
![[Pasted image 20241104114949.png]]

v-on还能调用传参，在后面加上括号里面写参数就行了
![[Pasted image 20241104131646.png]]
![[Pasted image 20241104131700.png]]

# v-bind
作用：动态的设置html的标签属性->src url  title  ...
语法：v-bind:属性名=“表达式”
![[Pasted image 20241104201737.png]]

觉得v-bind：太难写，这里有简写可以把v-bind省略掉，只留下：


# v-for
作用：基于数据循环，多次渲染整个元素->数组，对象，数字
![[Pasted image 20241104212703.png]]
遍历数组语法：
v-for=“(item，index) in 数组”
item：每一项 ，index 下标
如图所示
![[Pasted image 20241104213937.png]]

v-for中的key
![[Pasted image 20241105080308.png]]
语法：key属性=“唯一标识”
作用：给列表项添加的唯一标识，便于Vue进行列表项的正确排序复用
v-for的默认行为会尝试原地修改元素(就地复用)，比如列表第一条背景颜色是粉色，把他删掉后，上移的列表第一个还是粉色的
注意点：
1.key的值只能是字符串或数字类型
2.key的值必须具有唯一性
3.推荐使用id作为key(唯一)，不推荐使用index作为key(会变化，不对应)


# v-model
作用：给表单元素使用，双向数据绑定，可以快速获取或设置表单元素内容
- 数据变化，视图自动更新
- 视图变化，数据自动更新
语法：v-model：“变量名”，这个变量名是vue对象里面一个data的值
![[Pasted image 20241105082534.png]]
![[Pasted image 20241105081744.png]]