This is my git.
Git is free software.
Git Git Git.
//添加文件到git
把要添加的文件放在mygit目录下 /C/Users/Administrator/mygit

第一步，用命令git add告诉Git，把文件添加到仓库：
$ git add readme.txt
第二步，用命令git commit告诉Git，把文件提交到仓库：
$ git commit -m "wrote a readme file"
git commit命令，-m后面输入的是本次提交的说明。

git status命令可以让我们时刻掌握仓库当前的状态
git diff顾名思义就是查看difference
示例：$ git diff readme.txt

git log命令显示从最近到最远的提交日志
$ git log
如果嫌输出信息太多，加上--pretty=oneline参数：
$ git log --pretty=oneline

//回退到上一版本
在Git中，用HEAD表示当前版本
上一个版本是HEAD^，上上一个版本是HEAD^^，往上100个版本写成HEAD~100。
$ git reset --hard HEAD^

//再回去
找到上个版本的commit id 版本号没必要写全，前几位就可以了，Git会自动去找
$ git reset --hard 3628164
Git提供了一个命令git reflog用来记录你的每一次命令：（找commit id）
$ git reflog