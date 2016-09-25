cd ..         //退回到上层文件
cd D:/ 试试
ll            //查看所有文件
cd 试试       //进入“试试”文件夹
git init      //
git add readme.txt
git commit -m "statement"
git status
git log (--pretty=oneline)      //查看历史记录
git reset --hard HEAD^(或头指针)


查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>

创建+切换分支：git checkout -b <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>