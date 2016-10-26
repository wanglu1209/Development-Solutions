空空出品

《GitHub入门与实践》是本好书。
本文为个人笔记，非大众向，只有要点，没有解释！

---
#### 操作速记

git的工作方式：
`.git`: 附属于该仓库的工作树，对文件的操作都在该工作树中进行。

 Commad | 作用
 :---                          | :---
 `git init`                      | 初始化仓库，建立工作树
 `git status`                    | 查看仓库状态
 `git add file`                  | 将`file`从工作树添加到**暂存区**
 `git commit -m "discription"`   | 将改动的文件保存仓库的**历史记录**，不用`-m`会打开编辑器，可以记录该提交的详细信息
 `git log`                       | 查看提交日志
 `git log file`                  | 查看特定文件的提交日志
 `git log --pretty=short`        | 只查看提交日志的第一行
 `git log -p`                    | 显示文件的改动
 `git log --graph`               | 以图标形式查看日志
 `git diff`                      | 查看暂存区与工作树的差别(在add之后)
 `git diff HEAD`                 | 查看工作树与最新提交的差别(在commit)之后
 `git branch -a`                 | 显示分支一览
 `git checkout -b A`             | 创建并切换到分支A(不加`-b`则为切换)
 `git merge --no-ff A`           | 将分支A合并到当前分支，`--no-ff`是为了明确记录此次合并
 `git reset --hard hashcode(>4)` | 回溯当前分支到hashcode所在时间点的状态
 `git reflog`                    | 查看操作日志，配合`reset`。回溯前先查看日志找到hashcode
 `git commit --amend`            | 修改上一条提交信息
 `git rebase -i HEAD~2`          | 压缩最新的两个提交历史记录为一个，通常用于“Fix typo”(pick 改为 fixup)
 `git clone`                     | 获取远程仓库
 `git remote add origin gitPath` | 添加远程仓库，将名称设置为origin
 `git push -u origin master`     | 将当前分支推送给远程仓库origin的master分支，`-u`是将origin设置成当前分支的upstream
 `git checkout -b A origin/A`    | 获取origin仓库的A分支，命名为本地仓库的A分支
 `git pull origin A`             | 以origin的A分支为参照，更新当前所在分支
 `git fetch origin`              | 获取origin的最新数据，与本地master分支合并
 
#### 保持 fork 下来的本地仓库为最新数据

源码仓库为 A，将它 fork 下来到自己的仓库 B。

- clone B
```bash
git clone B
```

- 将 A 设置 upstream 的名称
```bash
git remote add upstream A
```

- 从 A 获取最新数据，与当前分支合并
```bash
git fetch upstram
```

#### 高效 Pull Request

- 一般操作是将项目 fork 下来，自己新建分支，在分支中修改，然后 Pull Request 新分支

- 边开发边讨论。有计划进行 Pull Request 时先发送 Pull Request，未开发完成时应在标题前加上`[WIP]`(Work In Progress)字样，以防误合并。

- 团队中，对一个仓库都具有编辑权限时，需要的时候直接创建分支，发送 Pull Request，免去 fork 的麻烦。
