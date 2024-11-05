需求：封装并导出基地址和求数组元素和的函数

默认标准使用：
1.导出：export default {}
2.导入：import 变量名 from ‘模块名或路径’

![[Pasted image 20241027082455.png]]
![[Pasted image 20241027082508.png]]

注意：Node.js默认支持CommonJS标准语法
如需使用ECMAScript标准语法，在运行模块所在文件夹新建package.json文件，并设置{"type":"module"}
![[Pasted image 20241027082808.png]]