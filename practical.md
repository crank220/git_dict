# 实用git

|   code    |   operate   |
|   ----    |   -------   |
| git init  | 在当前目录新建一个git代码库 |
| git clone [url] | 下载一个项目和它的整个代码历史 |
| git add .  | 添加当前目录的所有文件到暂存区 |
| git commit -m [message]  | 提交暂存区到仓库区 |
| git commit -a  | 提交工作区自上次commit之后到变化，直接到仓库区 |
| git branch  | 列出所有本地分支 |
| git branch -r  | 列出所有远程分支 |
| git branch [branch-name]  | 新建一个分支，但依然停留在当前分支 |
| git checkout -b [branch]  | 新建一个分支，并切换到该分支 |
| git branch [branch] [commit]  | 新建一个分支，指向指定到commit |
| git checkout [branch-name]  | 切换到指定分支，并更新工作区 |
| git merge [branch]  | 合并指定分支到当前分支 |
| git reset —merge  | 此方法会重置工作区的一切修改，慎用，但会保留暂存区的改动 |
| git branch -d [branch-name]  | 删除分支 |
| git push origin —delete [branch-name]    git branch -dr [remote/branch]  | 删除远程分支 |
| git fetch [remote]  | 下载远程仓库的所有变动 |
| git remote -v  | 显示所有远程仓库 |
| git remote show [remote]  | 显示某个远程仓库的信息 |
| git remote add [shortname] [url]  | 增加一个新的远程仓库，并命名 |
| git remote rm origin  | 删除远程仓库地址 |
| git remote set-url origin [url]  | 切换远程仓库地址（当代码库远程迁移后，修改本地代码关联的远程地址） |
| git pull [remote] [branch]  | 取回远程仓库的变化，并与本地分支合并 |
| git push [remote] [branch]  | 上传本次指定分支到远程仓库 |
| git push [remote] —force  | 强行推送当前分支到远程仓库，即使有冲突 |
| git reset —hard [commit]  | 重置当前分支的指针为commit，同时重置暂存区与工作区，与指定commit一致 |

```javascript
  git tag -a v2.1.18 -m '6月底合并前tag'  
  git push origin --tags
```