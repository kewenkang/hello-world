cd ..         //�˻ص��ϲ��ļ�
cd D:/ ����
ll            //�鿴�����ļ�
cd ����       //���롰���ԡ��ļ���
git init      //
git add readme.txt
git commit -m "statement"
git status
git diff 
git diff HEAD --readme.txt      //�鿴�������Ͱ汾���������°汾������
git checkout -- readme.txt      //��readme.txt�ļ��ڹ��������޸�ȫ���������������ݴ������״̬
git reset HEAD file             //���԰��ݴ������޸ĳ�����
rm test.txt                     //�ӹ�������ɾ�����ļ�
git rm test.txt                 //�Ӱ汾����ɾ�����ļ�(ɾ������checkout�ָ�)
git log (--pretty=oneline)      //�鿴��ʷ��¼
git reflog                      //�鿴�����޸ļ�¼
git reset --hard HEAD^(��ͷָ��)


�鿴��֧��git branch
������֧��git branch <name>
�л���֧��git checkout <name>
����+�л���֧��git checkout -b <name>
�ϲ�ĳ��֧����ǰ��֧��git merge <name>
git merge --no-ff dev           //Fast forwardģʽɾ����֧��ᶪ����֧��Ϣ
ɾ����֧��git branch -d <name>
ɾ��δ�ϲ��ķ�֧��git branch -D <name>

Ҫ����һ��Զ�̿⣬ʹ������git remote add origin git@server-name(github.com):path(kewenkang)/repo-name.git��
������ʹ������git push -u origin master��һ������master��֧���������ݣ�
�˺�ÿ�α����ύ��ֻҪ�б�Ҫ���Ϳ���ʹ������git push origin master���������޸�

Ҫ��¡һ���ֿ⣬���ȱ���֪���ֿ�ĵ�ַ��Ȼ��ʹ��git clone address(git@github.com:michaelliao/gitskills.git��https://github.com/michaelliao/gitskills.git) �����¡��
Git֧�ֶ���Э�飬����https����ͨ��ssh֧�ֵ�ԭ��gitЭ���ٶ����

��Git�޷��Զ��ϲ���֧ʱ���ͱ������Ƚ����ͻ�������ͻ�����ύ���ϲ���ɡ�
��git log --graph(git log --graph --pretty=oneline --abbrev-commit)������Կ�����֧�ϲ�ͼ

����ͷ����û�����ʱ���Ȱѹ����ֳ�git stashһ�£�Ȼ��ȥ�޸�bug���޸�����git stash pop(=git stash apply + git stash drop)���ص������ֳ�
�鿴������Ϣ��git stash list

�鿴Զ�̿���Ϣ��ʹ��git remote -v��
�����½��ķ�֧��������͵�Զ�̣��������˾��ǲ��ɼ��ģ�
�ӱ������ͷ�֧��ʹ��git push origin branch-name���������ʧ�ܣ�����git pullץȡԶ�̵����ύ��
�ڱ��ش�����Զ�̷�֧��Ӧ�ķ�֧��ʹ��git checkout -b branch-name origin/branch-name�����غ�Զ�̷�֧���������һ�£�
�������ط�֧��Զ�̷�֧�Ĺ�����ʹ��git branch --set-upstream branch-name origin/branch-name��
��Զ��ץȡ��֧��ʹ��git pull������г�ͻ��Ҫ�ȴ����ͻ��

����git tag <name>�����½�һ����ǩ��Ĭ��ΪHEAD��Ҳ����ָ��һ��commit id(ֱ�Ӽ��ں���)��
git tag -a <tagname> -m "blablabla..."����ָ����ǩ��Ϣ��
git tag -s(˽Կǩ��) <tagname> -m "blablabla..."������PGPǩ����ǩ��
����git tag���Բ鿴���б�ǩ��������git show <tagname>���Կ���˵�����֡�

����git push origin <tagname>��������һ�����ر�ǩ��
����git push origin --tags��������ȫ��δ���͹��ı��ر�ǩ��
����git tag -d <tagname>����ɾ��һ�����ر�ǩ��
����git push origin :refs/tags/<tagname>����ɾ��һ��Զ�̱�ǩ

����ĳЩ�ļ�ʱ����Ҫ��д.gitignore��
.gitignore�ļ�����Ҫ�ŵ��汾������ҿ��Զ�.gitignore���汾����
�����ȷʵ����Ӹ��ļ���������-fǿ����ӵ�Git��git add -f App.class

����git config --global alias.co checkout
git config --global alias.last 'log -1'
��ǰ�û���Git�����ļ������û���Ŀ¼�µ�һ�������ļ�.gitconfig��