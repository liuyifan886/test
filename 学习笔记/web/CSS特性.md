CSS特性作用：化简代码/定位问题，并解决问题
三大特性：继承性，层叠性，优先性
### 继承性
子集默认继承父级的文字控制属性
用法：直接在body标签里面设置文字控制属性，避免一个个给子标签设置重复的标签
有一种情况会继承失败，就是当子标签有自己的样式，就生效自己的样式，比如h1标签就不会继承字号，能继承颜色
### 层叠性
特点：
- 相同的属性会覆盖；后面的CSS属性覆盖前面的CSS属性
- 不同的属性会叠加；不同的CSS属性都生效

### 优先级
[[选择器]]
也叫权重，当一个标签使用了多种选择器时，基于不同种类的选择器的匹配规则
规则：选择器优先级高的样式生效
公式：通配符选择器<标签选择器<类选择器<id选择器<行内样式<！important
(范围越大，优先级越低)
！important：提高权重，优先度最高(谨慎使用)，在CSS属性里加上即可
