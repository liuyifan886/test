概念：一个免费开源，分布式的代码版本控制系统，帮助开发团队维护代码
如何学：
个人本机使用：Git基础命令和概念
多人共享使用：团队开发同一个项目的代码版本管理

#### Git安装
windows系统：exe程序，默认下一步即可
检验成功：
1.打开bash终端(git专用)
2.命令：git -v(查看版本号)


#### Git配置用户信息
配置：用户名和邮箱，应用在每次提交代码版本时表明自己身份
命令：
git 配置  全局  用户名 ***
git config --global user.name "itheima"
git config --global user.email "itheima@itcast.cn"
查看是否配置成功
git config --list，查看配置清单