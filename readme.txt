This is my git.
Git is free software.
Git Git Git.
//�����汾��
����һ���汾��ǳ��򵥣����ȣ�ѡ��һ�����ʵĵط�������һ����Ŀ¼��
$ mkdir learngit
$ cd learngit
$ pwd
/Users/michael/learngit
�ڶ�����ͨ��git init��������Ŀ¼���Git���Թ���Ĳֿ⣺
$ git init
Initialized empty Git repository in /Users/michael/learngit/.git/
������������Ҫgit���ļ��Ž�ȥ

//����ļ���git
��Ҫ��ӵ��ļ�����mygitĿ¼�� /C/Users/Administrator/mygit

��һ����������git add����Git�����ļ���ӵ��ֿ⣺
$ git add readme.txt
�ڶ�����������git commit����Git�����ļ��ύ���ֿ⣺
$ git commit -m "wrote a readme file"
git commit���-m����������Ǳ����ύ��˵����

git status�������������ʱ�����ղֿ⵱ǰ��״̬
git diff����˼����ǲ鿴difference
ʾ����$ git diff readme.txt

git log������ʾ���������Զ���ύ��־
$ git log
����������Ϣ̫�࣬����--pretty=oneline������
$ git log --pretty=oneline

//���˵���һ�汾
��Git�У���HEAD��ʾ��ǰ�汾
��һ���汾��HEAD^������һ���汾��HEAD^^������100���汾д��HEAD~100��
$ git reset --hard HEAD^

//�ٻ�ȥ
�ҵ��ϸ��汾��commit id �汾��û��Ҫдȫ��ǰ��λ�Ϳ����ˣ�Git���Զ�ȥ��
$ git reset --hard 3628164
Git�ṩ��һ������git reflog������¼���ÿһ���������commit id��
$ git reflog

����git checkout -- readme.txt��˼���ǣ���readme.txt�ļ��ڹ��������޸�ȫ������
��֮������������ļ��ص����һ��git commit��git addʱ��״̬��
$ git checkout -- readme.txt
���Ѿ�git add��������
������git reset HEAD file���԰��ݴ������޸ĳ�������unstage�������·Żع�������
$ git reset HEAD readme.txt
git reset����ȿ��Ի��˰汾��Ҳ���԰��ݴ������޸Ļ��˵�������
��ִ��git checkout���ڹ����������޸�

//ɾ���ļ�
$ rm test.txt
һ��ȷʵҪ�Ӱ汾����ɾ�����ļ����Ǿ�������git rmɾ��������git commit��
$ git rm test.txt
$ git commit -m "remove test.txt"
���ڣ��ļ��ʹӰ汾���б�ɾ���ˡ�

��һ�������ɾ���ˣ���Ϊ�汾���ﻹ���أ����Կ��Ժ����ɵذ���ɾ���ļ��ָ������°汾��
$ git checkout -- test.txt
git checkout��ʵ���ð汾����İ汾�滻�������İ汾�����۹��������޸Ļ���ɾ���������ԡ�һ����ԭ����

����git�Ѿ���github ��mygit����
��������ֻҪ���������ύ���Ϳ���ͨ�����
$ git push origin master
�ѱ���master��֧�������޸�������GitHub�����ڣ����ӵ���������ķֲ�ʽ�汾�⣡

//��Զ�̿��¡��Ŀ
$ git clone git@github.com:Zhou1eezZZ/gitskills.git

//������ϲ���֧
���ȣ����Ǵ���dev��֧��Ȼ���л���dev��֧��
$ git checkout -b dev
Switched to a new branch 'dev'
git checkout�������-b������ʾ�������л����൱�������������
$ git branch dev
$ git checkout dev
Switched to branch 'dev'
Ȼ����git branch����鿴��ǰ��֧��
$ git branch
* dev
  master
git branch������г����з�֧����ǰ��֧ǰ����һ��*�š�

Ȼ�����ǾͿ�����dev��֧�������ύ�������readme.txt�����޸�
Ȼ���ύ��
$ git add readme.txt 
$ git commit -m "branch test"
���ڣ�dev��֧�Ĺ�����ɣ����ǾͿ����л���master��֧��
$ git checkout master
Switched to branch 'master'
�л���master��֧���ٲ鿴һ��readme.txt�ļ����ղ���ӵ����ݲ����ˣ���Ϊ�Ǹ��ύ����dev��֧�ϣ���master��֧�˿̵��ύ�㲢û�б䣺
���ڣ����ǰ�dev��֧�Ĺ����ɹ��ϲ���master��֧�ϣ�
$ git merge dev
git merge�������ںϲ�ָ����֧����ǰ��֧��
�ϲ���ɺ󣬾Ϳ��Է��ĵ�ɾ��dev��֧�ˣ�
$ git branch -d dev
Deleted branch dev (was fec145a).

��Ϊ�������ϲ���ɾ����֧�ǳ��죬����Git������ʹ�÷�֧���ĳ�����񣬺ϲ�����ɾ����֧�����ֱ����master��֧�Ϲ���Ч����һ���ģ������̸���ȫ��

//�ϲ���ͻ
Git��<<<<<<<��=======��>>>>>>>��ǳ���ͬ��֧�����ݣ������޸����º󱣴� ���ύ
�ô�������git logҲ���Կ�����֧�ĺϲ������
$ git log --graph --pretty=oneline --abbrev-commit
*   59bc1cb conflict fixed
|\
| * 75a857c AND simple
* | 400b400 & simple
|/
* fec145a branch test
...
���ɾ��feature1��֧��
$ git branch -d feature1
Deleted branch feature1 (was 75a857c).
������ɡ�
��Git�޷��Զ��ϲ���֧ʱ���ͱ������Ƚ����ͻ�������ͻ�����ύ���ϲ���ɡ�

//��֧�������
ͨ�����ϲ���֧ʱ��������ܣ�Git����Fast forwardģʽ��������ģʽ�£�ɾ����֧�󣬻ᶪ����֧��Ϣ��
���Ҫǿ�ƽ���Fast forwardģʽ��Git�ͻ���mergeʱ����һ���µ�commit���������ӷ�֧��ʷ�ϾͿ��Կ�����֧��Ϣ��
׼���ϲ�dev��֧����ע��--no-ff��������ʾ����Fast forward��
$ git merge --no-ff -m "merge with no-ff" dev
Merge made by the 'recursive' strategy.
 readme.txt |    1 +
 1 file changed, 1 insertion(+)
��Ϊ���κϲ�Ҫ����һ���µ�commit�����Լ���-m��������commit����д��ȥ��
�ϲ���������git log������֧��ʷ��
$ git log --graph --pretty=oneline --abbrev-commit
*   7825a50 merge with no-ff
|\
| * 6224937 add merge
|/
*   59bc1cb conflict fixed
...
��ʵ�ʿ����У�����Ӧ�ð��ռ�������ԭ����з�֧����
���ȣ�master��֧Ӧ���Ƿǳ��ȶ��ģ�Ҳ���ǽ����������°汾��ƽʱ����������ɻ
�����ĸɻ��أ��ɻ��dev��֧�ϣ�Ҳ����˵��dev��֧�ǲ��ȶ��ģ���ĳ��ʱ�򣬱���1.0�汾����ʱ���ٰ�dev��֧�ϲ���master�ϣ���master��֧����1.0�汾��
������С�����ÿ���˶���dev��֧�ϸɻÿ���˶����Լ��ķ�֧��ʱ��ʱ����dev��֧�Ϻϲ��Ϳ����ˡ���ÿ������dev�µķ�֧��ɻ

//bug��֧
ÿ��bug������ͨ��һ���µ���ʱ��֧���޸����޸��󣬺ϲ���֧��Ȼ����ʱ��֧ɾ����
Git�ṩ��һ��stash���ܣ����԰ѵ�ǰ�����ֳ������ء����������Ժ�ָ��ֳ������������
$ git stash
Saved working directory and index state WIP on dev: 6224937 add merge
HEAD is now at 6224937 add merge
���ڣ���git status�鿴�����������Ǹɾ��ģ�������û�б�Git������ļ�������˿��Է��ĵش�����֧���޸�bug��
����ȷ��Ҫ���ĸ���֧���޸�bug���ٶ���Ҫ��master��֧���޸����ʹ�master������ʱ��֧��
$ git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 6 commits.
$ git checkout -b issue-101
Switched to a new branch 'issue-101'
�����޸�bug Ȼ���ύ
$ git add readme.txt 
$ git commit -m "fix bug 101"
[issue-101 cc17032] fix bug 101
 1 file changed, 1 insertion(+), 1 deletion(-)
�޸���ɺ��л���master��֧������ɺϲ������ɾ��issue-101��֧��
$ git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 2 commits.
$ git merge --no-ff -m "merged bug fix 101" issue-101
Merge made by the 'recursive' strategy.
 readme.txt |    2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
$ git branch -d issue-101
Deleted branch issue-101 (was cc17032).

�������Ǹɾ��ģ��ղŵĹ����ֳ��浽��ȥ�ˣ���git stash list�������
$ git stash list
stash@{0}: WIP on dev: 6224937 add merge

�����ֳ����ڣ�Git��stash���ݴ���ĳ���ط��ˣ�������Ҫ�ָ�һ�£��������취��
һ����git stash apply�ָ������ǻָ���stash���ݲ���ɾ��������Ҫ��git stash drop��ɾ����
��һ�ַ�ʽ����git stash pop���ָ���ͬʱ��stash����Ҳɾ�ˣ�
$ git stash pop

����Զ��stash���ָ���ʱ������git stash list�鿴��Ȼ��ָ�ָ����stash�������
$ git stash apply stash@{0}

//����Э��
���ͷ�֧
���ͷ�֧�����ǰѸ÷�֧�ϵ����б����ύ���͵�Զ�̿⡣����ʱ��Ҫָ�����ط�֧��������Git�ͻ�Ѹ÷�֧���͵�Զ�̿��Ӧ��Զ�̷�֧�ϣ�
$ git push origin master
���Ҫ����������֧������dev���͸ĳɣ�
$ git push origin dev
���ǣ�������һ��Ҫ�ѱ��ط�֧��Զ�����ͣ���ô����Щ��֧��Ҫ���ͣ���Щ����Ҫ�أ�
master��֧������֧�����Ҫʱ����Զ��ͬ����
dev��֧�ǿ�����֧���Ŷ����г�Ա����Ҫ�����湤��������Ҳ��Ҫ��Զ��ͬ����
bug��ֻ֧�����ڱ����޸�bug����û��Ҫ�Ƶ�Զ���ˣ������ϰ�Ҫ������ÿ�ܵ����޸��˼���bug��
feature��֧�Ƿ��Ƶ�Զ�̣�ȡ�������Ƿ�����С�����������濪����
��֮��������Git�У���֧��ȫ�����ڱ����Լ������棬�Ƿ����ͣ���������������

//��ǩ����
tag����һ���������׼�ס������������֣�����ĳ��commit����һ��
��Git�д��ǩ�ǳ��򵥣����ȣ��л�����Ҫ���ǩ�ķ�֧�ϣ�
$ git branch
* dev
  master
$ git checkout master
Switched to branch 'master'
Ȼ��������git tag <name>�Ϳ��Դ�һ���±�ǩ��
$ git tag v1.0
Ĭ�ϱ�ǩ�Ǵ��������ύ��commit�ϵġ���ʱ��������˴��ǩ
�������ҵ���ʷ�ύ��commit id��Ȼ����ϾͿ����ˣ�
$ git log --pretty=oneline --abbrev-commit
6a5819e merged bug fix 101
cc17032 fix bug 101
7825a50 merge with no-ff
6224937 add merge
59bc1cb conflict fixed
400b400 & simple
75a857c AND simple
fec145a branch test
d17efd8 remove test.txt
...
�ȷ�˵Ҫ��add merge����ύ���ǩ������Ӧ��commit id��6224937���������
$ git tag v0.9 6224937

��������git tag�鿴��ǩ��
$ git tag
v0.9
v1.0
ע�⣬��ǩ���ǰ�ʱ��˳���г������ǰ���ĸ����ġ�������git show <tagname>�鿴��ǩ��Ϣ��
$ git show v0.9
commit 622493706ab447b6bb37e4e2a2f276a20fed2ab4
Author: Michael Liao <askxuefeng@gmail.com>
Date:   Thu Aug 22 11:22:08 2013 +0800

    add merge
...
���Կ�����v0.9ȷʵ����add merge����ύ�ϡ�

�����Դ�������˵���ı�ǩ����-aָ����ǩ����-mָ��˵�����֣�
$ git tag -a v0.1 -m "version 0.1 released" 3628164

ɾ����ǩ
�����ǩ����ˣ�Ҳ����ɾ����
$ git tag -d v0.1
Deleted tag 'v0.1' (was e078af9)
��Ϊ�����ı�ǩ��ֻ�洢�ڱ��أ������Զ����͵�Զ�̡����ԣ����ı�ǩ�����ڱ��ذ�ȫɾ����
���Ҫ����ĳ����ǩ��Զ�̣�ʹ������git push origin <tagname>��
$ git push origin v1.0
Total 0 (delta 0), reused 0 (delta 0)
To git@github.com:michaelliao/learngit.git
 * [new tag]         v1.0 -> v1.0
���ߣ�һ��������ȫ����δ���͵�Զ�̵ı��ر�ǩ��
$ git push origin --tags
Counting objects: 1, done.
Writing objects: 100% (1/1), 554 bytes, done.
Total 1 (delta 0), reused 0 (delta 0)
To git@github.com:michaelliao/learngit.git
 * [new tag]         v0.2 -> v0.2
 * [new tag]         v0.9 -> v0.9
�����ǩ�Ѿ����͵�Զ�̣�Ҫɾ��Զ�̱�ǩ���鷳һ�㣬�ȴӱ���ɾ����
$ git tag -d v0.9
Deleted tag 'v0.9' (was 6224937)
Ȼ�󣬴�Զ��ɾ����ɾ������Ҳ��push�����Ǹ�ʽ���£�
$ git push origin :refs/tags/v0.9
To git@github.com:michaelliao/learngit.git
 - [deleted]         v0.9