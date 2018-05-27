# Git 常用命令
## 创建仓库文件夹
```
cd GitHub
mkdir learngit
cd leargit
pwd

192:~ xuemin$ cd GitHub/learngit/
192:learngit xuemin$ pwd
/Users/xuemin/GitHub/learngit
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

```
commit faf71b7ebf663211ce0f5995c29af600cd2a5bb1
Author: xpiao <xmin_02@163.com>
Date:   Sun May 27 15:42:57 2018 +0800

    append GPL

commit 4fa6de3615e435badfa6d97ab347449b6268a491
Author: xpiao <xmin_02@163.com>
Date:   Sun May 27 15:40:00 2018 +0800

    add distributed

commit b579646d10ba71ab20089f7167741968abc2fb5a
Author: xpiao <xmin_02@163.com>
Date:   Sun May 27 15:37:30 2018 +0800

    wrote a readme file

```

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

