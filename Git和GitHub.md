## GitHub

| repository   | 仓库                    |
| :----------- | ----------------------- |
| star         | 收藏                    |
| fork         | 克隆别人的仓库          |
| pull request | 发起合并请求            |
| watch        | 关注项目的更新          |
| issue        | 事物卡片，发现代码bug， |

| Github主页 |                                            |
| ---------- | ------------------------------------------ |
| 仓库主页   | https://github.com/TianyuSANG/myRepository |
| 个人主页   | https://github.com/TianyuSANG              |

| 创建仓库 | Create repository                 |
| -------- | --------------------------------- |
| 仓库管理 | Create File/Upload File/Find File |
|          | Edit File/Delete File             |
|          | Clone/Download                    |
|          | New issue/Close issue             |
|          | Star/Watch                        |
|          | Fork                              |
|          | Pull request/Merge request        |

开源项目共享方法

| 新建Issue    | 提交问题或者建议或者想法                   |
| ------------ | ------------------------------------------ |
| Pull Request | fork项目/修改自己仓发代码/发起pull request |



Github搭建个人站点：

新建Repository

库名:用户名.github.io

仓库中添加index.html文件，即为网站首页

访问链接: https://用户名.github.io

仅支持静态网页



Github搭建项目站点：

新建Repository

库名:用户名.github.io

个人仓库主页 Setting

Github Pages 选择分支，选择风格

访问：https://用户名.github.io/仓库名



## Git

Git管理Github托管项目



Git初始设置

| git config --global user.name "TianyuSANG"        | 设置用户名   用户名可以和Github账户名一致 |
| ------------------------------------------------- | ----------------------------------------- |
| git config --global user.email "815516304@qq.com" | 设置用户名邮箱                            |
| git config --list                                 |                                           |

 

初始化 增删改更新

| git init                 | 初始化本地仓库                    |
| ------------------------ | --------------------------------- |
| git add test.txt         | 将test.txt从工作区添加到暂存区    |
| git commit -m "注释内容" | 将文件从暂存区提交到本地仓库      |
| git status               | 查看工作区状态                    |
| git diff test.txt        | 查看文件变化内容                  |
| git log                  | 查看修改记录                      |
| git log --pretty=oneline | 一行显示git log                   |
| git reset --hard HEAD^   | 回退到上一个版本                  |
| git reflog               | 查看版本号                        |
| git reset --hard 版本号  | 回退到指定版本                    |
| git checkout --test.txt  | 丢弃工作区的修改   恢复删除的文件 |

创建SSH Key

| ssh-keygen  -t rsa –C “youremail@example.com” |
| --------------------------------------------- |
| 用户目录下生成id_rsa和id_rsa.pub这两个文件    |

Github上设置SSH，将id_rsa.pub内容复制过去



先有本地库，后有远程库，关联远程库  

远程创建Repository,

首次推送代码 git push -u origin master 加上-u参数，可以将本地mater和远程给master分支建立关联，以后可以简化为git push origin master

| command line | git init                                                    |
| ------------ | ----------------------------------------------------------- |
|              | git add README.md                                           |
|              | git commit -m "first commit"                                |
|              | git remote add origin https://github.com/TianyuSANG/123.git |
|              | git push -u origin master                                   |
| command line | git remote add origin https://github.com/TianyuSANG/123.git |
|              | git push -u origin master                                   |



先有远程库，后有本地库，克隆远程库

| command line | git clone https://github.com/TianyuSANG/123.git |
| ------------ | ----------------------------------------------- |
|              |                                                 |

创建与合并分支

| git checkout -b dev | 创建并却换到分支dev           |
| ------------------- | ----------------------------- |
| git branch          | 查看当前的分支                |
| git branch dev      | 创建分支dev                   |
| git checkout dev    | 切换到分支dev                 |
| git merge dev       | 在当前分支上合并dev分支内容跟 |
| git branch -d dev   | 删除dev分支                   |

git merge合并分支时，一般使用Fast forward模式，该模式下删除分支后，会丢掉分支信息

| git merge --no-ff -m "merge with no-ff" dev      | 合并dev分支 禁用fast forward模式 |
| ------------------------------------------------ | -------------------------------- |
| git log --graph --pretty=oneline --abbrev-commit |                                  |

工作没有做完，可以将工作现场隐藏起来

| git stash       | 将当前工作现场隐藏起来          |
| --------------- | ------------------------------- |
| git status      | 查看状态，干净的                |
| git stash list  | 查看隐藏的工作现场              |
| git stash apply | 恢复工作现场，stash内容仍需删除 |
| git stash drop  | 删除stash内容                   |

多人协作，从远程库clone，Git自动把本地的master分支和远程master分支对应起来了，

远程库的默认名称时origin

| git remote                                  | 查看远程库的信息                          |
| ------------------------------------------- | ----------------------------------------- |
| git remote -v                               | 详细信息                                  |
| git push origin master                      |                                           |
| git checkout -b dev origin/dev              | 创建远程origin的分支dev分支到本地来       |
| git pull                                    | 把最新的提交从origin/dev抓下来            |
| git branch --set-upstream-to=origin/dev dev | 设置本地dev分支和远程origin/dev分支的链接 |
| git pull                                    | pull成功，需要解决冲突                    |
| git push origin dev                         | 推送自己的修改                            |

