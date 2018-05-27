# Git 常用命令
## 创建仓库文件夹
```
cd GitHub
mkdir learngit
cd leargit

$ cd GitHub/learngit/
```

## 把仓库目录编程Git仓库
`git init`

## 查看隐藏目录
`ls -ah`
`.	..	.git` 
## 创建一个文件readme.txt
```
touch readme.txt
vi readme.txt
```
```
Git is a version control system.
Git is free software.
```

## 把文件添加到仓库
`git add readme.txt`

## 把文件提交到仓库
`git commit -m "wrote a readme file"`

```
[master (root-commit) b579646] wrote a readme file
 1 file changed, 2 insertions(+)
 create mode 100644 readme.txt
```

## 查看结果
`git status`

```
On branch master
Your branch is based on 'origin/master', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   readme.txt

```

## 查看文件修改内容
`git diff readme.txt`
```
*diff --git a/readme.txt b/readme.txt*
*index 46d49bf..9247db6 100644*
*--- a/readme.txt*
*+++ b/readme.txt*
@@ -1,2 +1,2 @@
-Git is a version control system.
+Git is a distributed version control system.
 Git is free software.
```

## 查看所有提交历史
`git log`

`git log —pretty=oneline`

```
faf71b7ebf663211ce0f5995c29af600cd2a5bb1 append GPL
4fa6de3615e435badfa6d97ab347449b6268a491 add distributed
b579646d10ba71ab20089f7167741968abc2fb5a wrote a readme file
```

## 回退版本 `HEAD^` `HEAD^^` `HEAD~100`
`git reset --hard HEAD^`
`HEAD is now at 4fa6de3 add distributed`

## 回到更新的版本
`git reset --hard faf71b`
`HEAD is now at faf71b7 append GPL`

## 查看所有命令历史
```
$ git reflog

faf71b7 HEAD@{0}: reset: moving to faf71
4fa6de3 HEAD@{1}: reset: moving to HEAD^
faf71b7 HEAD@{2}: commit: append GPL
4fa6de3 HEAD@{3}: commit: add distributed
b579646 HEAD@{4}: commit (initial): wrote a readme file
```

## 查看版本库和本地工作区两个文件的区别
```
git diff HEAD -- readme.txt

diff --git a/readme.txt b/readme.txt
index 76d770f..a9c5755 100644
--- a/readme.txt
+++ b/readme.txt
@@ -1,4 +1,4 @@
 Git is a distributed version control system.
 Git is free software distributed under the GPL.
 Git has a mutable index called stage.
-Git tracks changes.
+Git tracks changes of files.
```

## 丢弃工作区的修改，让文件回到最近一次`git commit` 或者 `git add` 时的内容
`git checkout -- readme.txt`

## `git add readme.txt`提交到了暂存区，撤销暂存区的修改，重新放回工作区：
```
git reset HEAD readme.txt
Unstaged changes after reset:
M    readme.txt
```

## 删除


