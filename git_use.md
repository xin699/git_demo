# git常用命令
## git本地仓库操作
- git init `初始化本地仓库`
- git add . `把仓库的文件添加到缓存区`   git add 单文件名 `提交单一文件到缓存区`
- git commit -u "提交描述" `把文件从缓存区提交到仓库`
- git status `查看文件状态`
- git diff `查看文件前后修改详情`

##版本回退
+ git log `查看版本历史提交记录`
+ git log --pretty=oneline `查看一行省略的提交记录`
+ git reflog `查看以前操作的明令，可以看到回退之前的版本号`
+ git reset --hard HEAD^ `会退到上一个版本`
+ git reset --hard HEAD^^ `会退到上上个版本`
+ git reset 版本号 `回退到相应的版本，版本号可简写，git log,git reflog可查看版本号`

##撤销修改
- git checkout -- 文件名 `撤销该次工作区的修改`
- git reset HEAD 文件名  `把暂存区的修改回退到工作区`

##删除文件
+ rm 文件名  `删除工作区文件`
+ git rm 文件名 `删除仓库文件` 然后  git commit -m '提交描述' 文件明  `提交一次`

##添加远程仓库
- git remote add origin https://github.com/xin699/git_demo.git `关联远程仓库`
- git push -u origin master `把本地库的所有内容推送到远程库上`  注释：origin: 默认和github关联的仓库，也就是我们要提交的仓库

##SSH验证
+ ls ~/.ssh/ `检查SSH key是否已经存在`
+ ssh-keygen -t rsa -b 2048 -C “your_email@example.com”  `如果第1步中的SSH key不存在，生成一个新的SSH key`
+ settings —- ssh and gpg keys —— new ssh key —- 粘贴 —- 保存 `在github操作`

##克隆代码
- git clone git@github.com:michaelliao/gitskills.git 、在github找到相应项目地址，克隆下来、

##创建与合并分支
+ git branch <name> `创建分支`
+ git checkout <name> `切换分支`
+ git checkout -b <name> `创建并切换分支`
+ git branch  `查看分支`
+ git merge <name> `合并某分支到当前分支`
+ git log --graph --pretty=oneline --abbrev-commit  `查看分支合并情况`
+ git branch -d <name>  `删除分支`