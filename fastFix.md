# 快速修复

## 撤销

> 情况一：文件被修改了，但未执行git add操作(working tree内撤销)

-  git checkout fileName
-  git checkout .

> 情况二：同时对多个文件执行了git add操作，但本次只想提交其中一部分文件
-  git add *
-  git status

1. 取消暂存
-  git reset HEAD [filename]

> 情况三：文件执行了git add操作，但想撤销对其的修改（index内回滚）

1. 取消暂存
-  git reset HEAD fileName
2. 撤销修改
_  git checkout fileName

> 情况四：修改的文件已被git commit，但想再次修改不再产生新的Commit

1. 修改最后一次提交 
-  git add sample.txt
-  git commit --amend -m"说明"

> 情况五：已在本地进行了多次git commit操作，现在想撤销到其中某次Commit

-  git reset [--hard|soft|mixed|merge|keep] [commit|HEAD]

## 回滚

> 情况一：撤销指定文件到指定版本

1. 查看指定文件的历史版本  
-  git log <filename>
2. 回滚到指定commitID  
-  git checkout <commitID> <filename>

> 情况二：删除最后一次远程提交
1. 使用revert
-  git revert HEAD
-  git push origin master
2. 使用reset
-  git reset --hard HEAD^
-  git push origin master -f
3. 二者区别：
-  revert是放弃指定提交的修改，但是会生成一次新的提交，需要填写提交注释，以前的历史记录都在；
-  reset是指将HEAD指针指到指定提交，历史记录中不会出现放弃的提交记录。

> 情况三：回滚某次提交
1.  找到要回滚的commitID
-  git log
-  git revert commitID

## 删除
1. git log --oneline -n5
  
2. git rebase -i "5b3ba7a"^
-  需要注意最后的^号，意思是commit id的前一次提交

3. git push origin master -f

### 在编辑框中删除相关commit，如pick 5b3ba7a test2，然后保存退出（如果遇到冲突需要先解决冲突）！

#### 通过上述操作，如果你想对历史多个commit进行处理或者，可以选择git rebase -i，只需删除对应的记录就好。rebase还可对 commit 消息进行编辑，以及合并多个commit。

[参考](https://blog.csdn.net/asoar/article/details/84111841)
