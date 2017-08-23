This is my git.
Git is free software.
Git Git Git.
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