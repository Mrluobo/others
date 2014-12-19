`psw` 命令用于显示当前目录。
`git init` 初始化git
`git add` 把文件添加到仓库
`git commit` 提交到仓库 `-m "xxx"`提交说明
`git status` 仓库当前的状态
`git diff` 查看`difference`
`git log` 查看所有版本历史记录`--pretty=oneline` 不显示作者 格式化历史记录
首先，Git必须知道当前版本是哪个版本，在Git中，用HEAD表示当前版本，也就是最新的提交“ 3628164...882e1e0”（注意我的提交ID和你的肯定不一样），上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100。
`git reset` 回到某个版本 `--hard`
                     `HEAD file` 将暂存区的修改回退到工作区
`git reflog` 来记录你的每一次命令
`git checkout --file`	 用来撤销修改
`origin` 远程库
`git remote add origin` +远程库地址 创建远程连接
`git push -u origin master` 推送到远程库
         `-u` 将远程库的master 分支和本地master分支关联
`git checkout -b dev` 创建新的分支
         `-b`表示同时切换  `/origin/dev`创建远程dev分支到本地
`git checkout -b dev` == `git branch dev git checkout dev`
`git checkout master` 切换回master分支
`git merge dev` 将dev分支合并到当前分支
`git branch -d dev` 删除dev 分支
`git stash` 将现在的工作区存储起来
`git stash list` 查看stash的内容
`git stash apply` 回复 git stash 暂存的工作区但不删除需要通`过git stash drop`来删除
`git stash pop` 恢复工作区的通天干事删除stash 的内容
`git branch --set-upstream dev origin/dev` 指定本地`dev`和远程`origin/dev`分支的链接
`git tag name` 给当前分支打标签 也可 `-a name -m` 说明 末尾指定commit给指定commit打标签



