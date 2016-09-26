cd ..         //退回到上层文件
cd D:/ 试试
ll            //查看所有文件
cd 试试       //进入“试试”文件夹
git init      //
git add readme.txt
git commit -m "statement"
git status
git diff 
git diff HEAD --readme.txt      //查看工作区和版本库里面最新版本的区别
git checkout -- readme.txt      //把readme.txt文件在工作区的修改全部撤销，撤销到暂存区里的状态
git reset HEAD file             //可以把暂存区的修改撤销掉
rm test.txt                     //从工作区中删除该文件
git rm test.txt                 //从版本库中删除该文件(删除可用checkout恢复)
git log (--pretty=oneline)      //查看历史记录
git reflog                      //查看所有修改记录
git reset --hard HEAD^(或头指针)


查看分支：git branch
创建分支：git branch <name>
切换分支：git checkout <name>
创建+切换分支：git checkout -b <name>
合并某分支到当前分支：git merge <name>
git merge --no-ff dev           //Fast forward模式删除分支后会丢掉分支信息
删除分支：git branch -d <name>
删除未合并的分支：git branch -D <name>

要关联一个远程库，使用命令git remote add origin git@server-name(github.com):path(kewenkang)/repo-name.git；
关联后，使用命令git push -u origin master第一次推送master分支的所有内容；
此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改

要克隆一个仓库，首先必须知道仓库的地址，然后使用git clone address(git@github.com:michaelliao/gitskills.git或https://github.com/michaelliao/gitskills.git) 命令克隆。
Git支持多种协议，包括https，但通过ssh支持的原生git协议速度最快

当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。
用git log --graph(git log --graph --pretty=oneline --abbrev-commit)命令可以看到分支合并图

当手头工作没有完成时，先把工作现场git stash一下，然后去修复bug，修复后，再git stash pop(=git stash apply + git stash drop)，回到工作现场
查看储存信息用git stash list

查看远程库信息，使用git remote -v；
本地新建的分支如果不推送到远程，对其他人就是不可见的；
从本地推送分支，使用git push origin branch-name，如果推送失败，先用git pull抓取远程的新提交；
在本地创建和远程分支对应的分支，使用git checkout -b branch-name origin/branch-name，本地和远程分支的名称最好一致；
建立本地分支和远程分支的关联，使用git branch --set-upstream branch-name origin/branch-name；
从远程抓取分支，使用git pull，如果有冲突，要先处理冲突。

命令git tag <name>用于新建一个标签，默认为HEAD，也可以指定一个commit id(直接加在后面)；
git tag -a <tagname> -m "blablabla..."可以指定标签信息；
git tag -s(私钥签名) <tagname> -m "blablabla..."可以用PGP签名标签；
命令git tag可以查看所有标签；用命令git show <tagname>可以看到说明文字。

命令git push origin <tagname>可以推送一个本地标签；
命令git push origin --tags可以推送全部未推送过的本地标签；
命令git tag -d <tagname>可以删除一个本地标签；
命令git push origin :refs/tags/<tagname>可以删除一个远程标签

忽略某些文件时，需要编写.gitignore；
.gitignore文件本身要放到版本库里，并且可以对.gitignore做版本管理
如果你确实想添加该文件，可以用-f强制添加到Git：git add -f App.class

别名git config --global alias.co checkout
git config --global alias.last 'log -1'
当前用户的Git配置文件放在用户主目录下的一个隐藏文件.gitconfig中