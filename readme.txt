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

命令git checkout -- readme.txt意思就是，把readme.txt文件在工作区的修改全部撤销
总之，就是让这个文件回到最近一次git commit或git add时的状态。
$ git checkout -- readme.txt
若已经git add到缓存区
用命令git reset HEAD file可以把暂存区的修改撤销掉（unstage），重新放回工作区：
$ git reset HEAD readme.txt
git reset命令既可以回退版本，也可以把暂存区的修改回退到工作区
再执行git checkout能在工作区撤销修改

//删除文件
$ rm test.txt
一是确实要从版本库中删除该文件，那就用命令git rm删掉，并且git commit：
$ git rm test.txt
$ git commit -m "remove test.txt"
现在，文件就从版本库中被删除了。

另一种情况是删错了，因为版本库里还有呢，所以可以很轻松地把误删的文件恢复到最新版本：
$ git checkout -- test.txt
git checkout其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。

本地git已经和github 的mygit连接
从现在起，只要本地作了提交，就可以通过命令：
$ git push origin master
把本地master分支的最新修改推送至GitHub，现在，你就拥有了真正的分布式版本库！

//从远程库克隆项目
$ git clone git@github.com:Zhou1eezZZ/gitskills.git

//创建与合并分支
首先，我们创建dev分支，然后切换到dev分支：
$ git checkout -b dev
Switched to a new branch 'dev'
git checkout命令加上-b参数表示创建并切换，相当于以下两条命令：
$ git branch dev
$ git checkout dev
Switched to branch 'dev'
然后，用git branch命令查看当前分支：
$ git branch
* dev
  master
git branch命令会列出所有分支，当前分支前面会标一个*号。

然后，我们就可以在dev分支上正常提交，比如对readme.txt做个修改
然后提交：
$ git add readme.txt 
$ git commit -m "branch test"
现在，dev分支的工作完成，我们就可以切换回master分支：
$ git checkout master
Switched to branch 'master'
切换回master分支后，再查看一个readme.txt文件，刚才添加的内容不见了！因为那个提交是在dev分支上，而master分支此刻的提交点并没有变：
现在，我们把dev分支的工作成果合并到master分支上：
$ git merge dev
git merge命令用于合并指定分支到当前分支。
合并完成后，就可以放心地删除dev分支了：
$ git branch -d dev
Deleted branch dev (was fec145a).

因为创建、合并和删除分支非常快，所以Git鼓励你使用分支完成某个任务，合并后再删掉分支，这和直接在master分支上工作效果是一样的，但过程更安全。