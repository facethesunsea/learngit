git init  初始化一个GIT仓库

git add <file> 添加文件  可以多次使用这个命令添加多个文件
git commit -m <message>  一次提交所有的文件

// 这里是查看状态修改
git status  显示工作区的状态，提示修改未add or commit
git  diff <file>  查看被修改的内容

// 这里开始版本回退
HEAD 指向当前版本
git reset --hard commit_id  回退或返回未来的某个版本  commit_id可以是id，也可以写成HEAD^ or HEAD~1回退到某个版本
git log 可以查看提交历史 便于确定要回退到哪个版本  后面加上 --pretty=online让内容显示为一行
git reflog  查看命令历史 便于确定要回到未来的哪个版本

// 撤销修改
git checkout -- <file>   撤销工作区的修改
git reset HEAD <file>  撤销提交到缓冲区的修改

// 删除文件
rm <file>   工作区删除文件
git rm <file>   删除文件添加到缓冲区
git commit -m <message>   提交删除

//本地创建SSH Key
ssh-keygen -t rsa -C "youremail@example.com"

// 本地仓库的内容推送到GitHub仓库
git remote add origin git@github.com:account/learngit.git 本地库与git仓库关联   origin是远程库的名字
若是出现已存在的错误  就先删除：git remote rm origin
git push -u origin master   //本地得当前分支master推送到远程，并且把远程的master与本地的master关联起来，可以简化命令  远程是空的需要添加-u参数 


// 克隆
git clone git@github.com:account/repository.git  从远程克隆到本地
git支持多种协议，包括https git（更快）

// 创建分支和合并分支
git checkout -b dev  创建并切换分支dev  相当于这两个命令： git branch dev + git checkout dev
git branch  查看当前分支
git merge dev  合并指定分支dev到当前分支：这个命令前先切换分支到要合并的那个分支
    --结果信息：Fast-forward 表示这次合并是“快进模式”
git branch -d dev  删除dev分支