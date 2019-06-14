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