## 1day

### 日志切割

​	步骤

​		1.创建切换shell脚本

​		2.使用linux任务

### 匹配

**类型**

​	=/ 精准

​	^~某字符开头

​	~* 正则匹配

**location 匹配流程图**

![](E:\MindManager\java\git\java\服务端\nginx\享学vip\asserts\localtionflow.PNG)

### 知识点

#### shell脚本详解

​	1.使用mv指令 切割日志

​	2.使用 kill指令 发送 user1信号给nginx。

​	KILL 9 强行杀是程序

#### nginx 信号类型

​	1.TERM、INT快速关闭

​	2.QUIT从容关闭

​	3.HUP平滑重启，重新加载配置文件

​	4.USER1 重新打开日志

​	5.USER2平滑升级可执行程序

