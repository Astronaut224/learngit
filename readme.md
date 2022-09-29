# Git学习

## Git的基础概念

### 1. Git中的3个区域

工作区：处理工作的目录

暂存区：已完成的工作临时存放区域，等待被提交

Git仓库：最终存放的区域

工作流程：工作区编写代码 --> 代码写好存放暂存区 --> 全部完成提交仓库



### 2. Git配置

1. 配置用户信息：

```cmd
git config --global user.name ""
git config --global user.email ""
```

这两条命令会写入C:/Users/用户名文件夹/.gitconfig ，这是Git全局配置文件，配置一次永久生效。

2. 获取帮助手册：

```
git help 命令
或
git 命令 -h
```

### 3. Git使用

1. 在现有目录中初始化Git仓库

```
git init
```

2. 检查文件状态

```
git status 文件
git status -s
```

文件状态有：

未跟踪Untracked：不被Git管理

未修改Unmodified：工作区中和Git仓库中文件内容一致

已修改Modified：工作区中和Git仓库中文件内容不一致

已暂存Staged：工作区中修改的文件已经放到暂存区

3. 跟踪新文件（或整个目录）

```
git add 文件
或
git add 目录
```

4. 提交更新

```
git commit -m '描述'
```

5. Git忽略

添加 .gitignore 文件，文件中添加需要忽略的文件。

## 关联远程仓库

1. SSH

生成ssh key：

```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

三次回车后会在 `C:\Users\用户名文件夹\.ssh` 下会生成 id_rsa 和 id_rsa.pub 两个文件

配置SSH key 到github上。

创建远程仓库后，关联到本地仓库：

```
git remote add origin 地址
git push -u origin master
```

## 分支

1. 查看分支

```
git branch
* master	// *号表示当前所处的分支
```

2. 创建分支

```
git branch 新分支名字	// 不会切换分支，当前还是处于master分支
```

3. 切换分支

```
git checkout 新分支名字
```

4. 创建并切换分支

```
git checkout -b 新分支名字
// 注意需要当前分支是主分支，所以要先切换到master
```

5. 合并分支

```
git checkout master		// 切换到主分支上
git merge 新分支名字		// 合并分支
```

6. 删除分支

```
git branch -d 分支名字
```

7. 将本地分支推送到远程仓库

```
git push -u 远程仓库别名 本地分支名称:远程分支名称
git push -u origin test		//让远程分支和本地分支名称保持一致，简略写法
```

8. 查看远程仓库中的分支列表

```
git remote show 远程仓库名称
```

9. 跟踪分支

```
git checkout 远程分支名字
```

10. 拉取分支

```
git pull
```

