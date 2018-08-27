# Git Tips

### 初始化 Git 仓库

```bash
$ git init
```

###  版本回退

#### 回退到上一个版本

```bash
$ git reset --hard HEAD^
```

#### 回退到上上个版本

```bash
$ git reset --hard HEAD^^
```

#### 回退到指定版本

``` bash
$ git reset --hard <commit id>
```

#### 撤销工作区修改

```bash
$ git checkout -- <filename>
```

#### 从暂存区撤销修改 (git add)

```bash
$ git reset HEAD <filename>
```

### 日志记录

#### 查看 commit 记录

```bash
$ git log
```

#### 查看命令记录

```bash
$ git reflog
```

### 远程仓库

#### 添加远程仓库

```bash
$ git remote add origin git@github.com:username/repo_name.git
```

#### 推送并关联远程仓库

```bash
$ git push -u origin master
```

#### 查看远程仓库信息

```bash
$ git remote
$ git remote -v
```

### 分支

#### 创建并切换分支

```bash
$ git checkout -b <branch name>
```

#### 创建分支

```bash
$ git branch <branch name>
```

#### 切换分支

```bash
$ git checkout <branch_name>
```

#### 合并分支

```bash
$ git merge <branch_name>
# 禁止 Fast-Forward
$ git merge --no-ff -m "<message>" <branch name>
```

#### 链接远程分支

```bash
$ git branch --set-upstream-to=origin/<origin branch name> <local branch name>
```

#### 删除分支

```bash
$ git branch -d <branch ame>
```

#### 分支合并图

```bash
$ git log --graph
$ git log --graph --pretty=oneline --abbrev-commit
```

#### 变基

```bash
$ git rebase
```

### 暂存

#### 暂时储存

```bash
$ git stash
```

#### 查看 stash

```bash
$ git stash list
```

#### 恢复&删除

```bash
$ git stash apply
$ git stash drop
$ git stash pop
```

###  标签

#### 为当前分支的最新 commit 添加标签

```bash
$ git tag <tag-name>
$ git tag -a <tag-name> -m <message>
```

#### 为某个 commit 添加标签

```bash
$ git tag <tag-name> <commit-id>
```

#### 查看标签信息

```bash
$ git show <tag-name>
```

#### 删除标签

```bash
$ git tag -d <tag-name>
```

