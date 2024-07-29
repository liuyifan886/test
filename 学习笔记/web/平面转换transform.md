作用：为元素添加动态效果，一般与过渡配合使用
概念：改变盒子在平面内的状态(位移，旋转，缩放，倾斜)


### 平面转换-位移
属性：
transform：translate(x轴移动距离，y轴移动距离)

取值
- 像素单位数值
- 百分比(参照盒子自身尺寸计算结果)
- 正负均可
![[Pasted image 20240603081939.png]]

技巧
- translate()只写一个值，表示沿着x轴移动
- 单独设置x或y轴移动距离：translateX()或者translateY()



### 平面转换-旋转
属性：
transform：rotate(旋转角度)
角度单位是deg
技巧
- 取值正负均可
- 取值为正，顺时针旋转
- 取值为负，逆时针旋转



### 平面转换-改变转换原点
默认情况下，转换原点是盒子中心点
属性：transform-origin：水平原点位置  垂直原点位置
取值
- **方位名词(常用)**(left，top，right，bottom，center)
- 像素单位数值
- 百分比


### 平面转换-多重转换
技巧，先平移再旋转
transform:translate  rotate
原理：旋转会改变主轴方向，多重转换以第一种转换形态的坐标轴为准



### 平面转换-缩放
属性
transform：scale(缩放倍数)
transform：scale(x轴缩放倍数，y轴缩放倍数)
技巧
- 通常，只为scale()设置一个值，表示x轴和y轴等比例缩放
- 取值大于1表示放大，取值小于1表示缩小


### 平面转换-倾斜
属性
transform:skew()
取值
角度度数deg