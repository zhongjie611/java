工作区域

​	三个

​		git 仓库 repository

​			最终文件 保持到仓库，新版本		

​		暂存区	

​			暂存已修改的文件

​		工作区 woking directory

​			添加编辑修改文件

两种方式提交

​	图形 命令

​	学习命令

步骤

- [ ] ​	提交git add   （工作区-》暂存区）
	 [ ] ​	确定提交文件 情况 get status
	 [ ] ​	git commit -m 提交描述 （暂存到仓库）
	 [ ] ​	再次查看状态 git status			

初始化

​	新建文件 右键 git here base

​		输入

​			用户名$ git config --global user.name ‘zhongjie611’

​			邮箱$ git config --global user.email ‘107619706@qq.com’

​			查看设置

​	再次 新建文件 右键or linux命令 mkdir

​		进入新文件 cd test

​			输入 git init 生成隐藏文件.git（存储本地仓库信息）

**向本地仓库**中添加文件 四步 步骤上面 步骤 linux 命令

1. **创建文件 touch a1**.java
2. git init 初始化
3.  git status
4. 删除 rm
5. git status
6. touch a1.java
7. git status 查看状态 提示 通过git add 提交 暂存区
8. git add 文件名 添加暂存区
9. 查看状态
10. 提交到仓库 git commit -m
11. git status
12. **修改文件 vi 文件**
13. cat 文件 内容查看
14. git status 提示已修改
15. git add 暂存区
16. git status 
17. git add 仓库
18. git commit -m ’ ’输入描述 
19. **删除文件 rm -rf 文件名**
20. git rm 文件 从git删除
21. git commit -m ‘第一次删除’
22. git status  工作空间干净 working clear

**远程仓库**作用 备份共享

![1556374856097](D:\java\笔记\git\1556374856097.png)

1. 克隆 目的：将远程项目复制到本地			
2. ![1556375041752](D:\java\笔记\git\1556375041752.png)
3. git clone 地址
4. git config --list 查看配置信息
5. vi a1.java
6. git add a1.java
7. git status
8. git commit -m ''
9. git status
10. git push 推到远程仓库
11. ![1556376706745](D:\java\笔记\git\1556376706745.png)
12. 输入密码提交、
13. 推送失败 没有设置登录密码 提示无权限 403
14. 修改账户 vi 或者 .git里面config文件
15. ![1556376202599](D:\java\笔记\git\1556376202599.png)
16. 设置权限

**个人网站**

访问 https 用户名.github.io

点猫头

新建仓库 new repository

仓库名 用户名.github.io

​	描述填入

- [x] ​	public
	 [x] ​	initiallze this repository with a readme

访问 404

​	创建index.html

仓库自动生成主题页面

1.点击域名 https 用户名 github.io/项目名

2.进入项目 setting 【】

3  下拉找到【launch automatic page generator】自动生成主题页面

3  输入项目名称 项目 描述

4 提交 选择主题 点击public page

5 提示访问 显示 OK、



分支

```
git branch -r       #查看远程所有分支

git branch           #查看本地所有分支

git branch -a       #查看本地及远程的所有分支，如下图

git fetch   #将某个远程主机的更新，全部取回本地：

git branch -a  #查看远程分支

git branch  #查看本地分支：

git checkout 分支 #切换分支：

git push origin -d 分支名  #删除远程分支: 

 git branch -d 分支名  #删除本地分支

git remote show origin  #查看远程分支和本地分支的对应关系

git remote prune origin #删除远程已经删除过的分支
```