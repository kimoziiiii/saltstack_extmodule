saltstack_extmodule
===
项目描述
---
基于saltstack开发的模块，为了实现集中和自动的控制众多的服务器，使用时需要搭建saltstack环境
###### 目前实现的功能
1. 实现JAVA应用的自动检查、发布、回滚操作

运行环境
---
1. python2.6
2. saltstack 2015.+
3. linux

安装使用
---
1. 把主模块`appdeplpy.py`放到saltstack的指定环境中，如放到`base`环境中，默认的目录是`/srv/salt/base/_module/`,
   在salt master上执行命令：
```bash
salt <target> saltutil.sync_module
```
   该命令用于传输或更新salt minion 模块
2. 从pillar_struc目录中拷贝里面的所有文件存放到如`base`环境的pillar目录`/srv/salt/pillar`
   执行命令：
```bash
salt <target> saltutil.pillar_refresh
```
   该命令用于更新pillar数据
3. 执行命令
```bash
salt <target> appdeploy.<function> <*args>
```

参考文档
---
1. salt安装文档 https://docs.saltstack.com/en/latest/topics/installation/index.html, 推荐使用salt-bootstrap进行安装。
2. 快速了解saltstack请查看PPT文档：`SaltStack扩散手册.ppt`

TODO
---
- 和WEB联调
- .....
- 测试


