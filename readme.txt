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