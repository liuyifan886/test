表示当前虚拟机的运行环境，该类不是静态类，想要调用需要先创立对象，但是不能直接new，该类的构造方法是私有的，要通过一个静态方法去调用，getRuntime()
具体原因:一个电脑只能有一个虚拟环境，创建多个没有意义
![[Pasted image 20240408100012.png]] 
![[Pasted image 20240408101522.png]]


其他方法:exit().作用为停止虚拟机,实际上从底层来看[[System类]]的exit方法就是调用的Runtime类的

availableProcessors():获得cpu的线程数
![[Pasted image 20240408101457.png]]

maxMemory():JVM总共能从系统中获取的总内存大小,单位byte
![[Pasted image 20240408101719.png]]

totalMemoty():JVM已经从系统中获取的内存大小，单位byte
![[Pasted image 20240408101916.png]]

freeMemory():JVM剩余内存大小，单位byte
![[Pasted image 20240408102206.png]]

exec():运行cmd命令，不是所有的命令都能执行，可打开系统里的一些软件
![[Pasted image 20240408102532.png]]
直接调用一般出错，按快捷键alt加回车，解决问题选第一个方法，没第一个才选第二个
![[Pasted image 20240408102740.png]]
该方法学到异常时会了解[[异常]]
一些好玩的指令:
![[Pasted image 20240408103434.png]]


