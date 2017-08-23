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