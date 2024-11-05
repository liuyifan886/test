问题：有时候别人做完项目给我们传文件，文件里面不会有软件包node_modules，但是会有package.json,package-lock.json，这是为啥

因为我们可以自己下载本地依赖的软件包，自己用npm下载依赖比磁盘传递拷贝要块的多

怎么下载：项目终端(根目录)输入命令：npm i
下载package.json中记录的所有软件包