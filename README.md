# gitDemo
### 
git clone https://github.com/songlin0859/gitDemo.git //checkout远程git
cd gitDemo/ //进入文件所在文件夹
git branch //查看当前有哪些分支
* master //"*标记的是当前所在的分支"

git status //查单当前的状态 这个随便用
git add README.md //添加文件 
git add . //添加所有文件
git commit -m "test vi" //提交文件
git log //查看提交记录
```
	commit 7794d3d16a342271af2b6d697e24b9afaad970af (HEAD -> master)
	Author: chensonglin <csl@differsoft.com>
	Date:   Wed Sep 30 09:41:36 2020 +0800

		test vi

	commit c33015e67ffcf110270ff44bb37592099c52c95f (origin/master, origin/HEAD)
	Author: 松林 <songlin0859@users.noreply.github.com>
	Date:   Wed Sep 30 09:29:36 2020 +0800

		Initial commit
```

git log --pretty=oneline //单行显示log信息
```
	7794d3d (HEAD -> master) test vi
	c33015e (origin/master, origin/HEAD) Initial commit
```

git branch develop //新建develop分支（不切换分支） 如果分支存在 报错 “fatal: A branch named 'develop' already exists.”
git branch //查看分支
  develop
* master

git checkout feature/gitTag //切换到某个分支 如果分支不存在 报错  “error: pathspec 'feature/gitTag' did not match any file(s) known to git.”


git checkout -b feature/gitTag //切换到某个分支 如果分支不存在 则新建分支再切换到该分支
Switched to a new branch 'feature/gitTag'
git branch //查看分支
  develop
* feature/gitTag
  master


$ dir //查看目录下的文件
README.md
$ ls  //查看目录下的文件
README.md



git tag //查看tag
git tag v0.0.1 //打标签

git tag
v0.0.1

git tag show v0.0.1 //标签里面有空格 则取空格前面的内容
git tag
show
v0.0.1

git tag "show v0.0.1 " //标签内容不要家单引号或者双引号 会报错
fatal: 'show v0.0.1 ' is not a valid tag name.
git tag 'show v0.0.1'
fatal: 'show v0.0.1' is not a valid tag name.

git tag -d show //删除 show 标签 （删除本地的标签）
Deleted tag 'show' (was 7794d3d)
git tag
v0.0.1

git show v0.0.1 // 查看标签详情
```
	commit 7794d3d16a342271af2b6d697e24b9afaad970af (HEAD -> feature/gitTag, tag: v0.0.1, master, develop)
	Author: chensonglin <csl@differsoft.com>
	Date:   Wed Sep 30 09:41:36 2020 +0800

		test vi

	diff --git a/README.md b/README.md
	index 62a40f9..14712e1 100644
	--- a/README.md
	+++ b/README.md
	@@ -1,2 +1,4 @@
	 # gitDemo
	 git demo
	+1. cd <git dir>;
	+2. git branch 查看git的分支;
```
git log --pretty=oneline //查看提交记录
a1f8848bb04b768dd68a54874253a51deb2e3fa5 (HEAD -> feature/gitTag) for tag
7794d3d16a342271af2b6d697e24b9afaad970af (tag: v0.0.1, master, develop) test vi
c33015e67ffcf110270ff44bb37592099c52c95f (origin/master, origin/HEAD) Initial commit

git tag -a v1.0 -m "annotation tag" //打带注释的标签
git tag
v0.0.1
v1.0

git show v1.0
```
	tag v1.0
	Tagger: chensonglin <csl@differsoft.com>
	Date:   Wed Sep 30 09:49:30 2020 +0800

	annotation tag

	commit a1f8848bb04b768dd68a54874253a51deb2e3fa5 (HEAD -> feature/gitTag, tag: v1.0)
	Author: chensonglin <csl@differsoft.com>
	Date:   Wed Sep 30 09:48:42 2020 +0800

		for tag

	diff --git a/README.md b/README.md
	index 14712e1..627bc41 100644
	--- a/README.md
	+++ b/README.md
	@@ -2,3 +2,7 @@
	 git demo
	 1. cd <git dir>;
	 2. git branch 查看git的分支;
	+
	+测试tag 随便输入点啥
	+哈哈哈哈
	+
```

git log --pretty=oneline
a1f8848bb04b768dd68a54874253a51deb2e3fa5 (HEAD -> feature/gitTag, tag: v1.0) for tag
7794d3d16a342271af2b6d697e24b9afaad970af (tag: v0.0.1, master, develop) test vi
c33015e67ffcf110270ff44bb37592099c52c95f (origin/master, origin/HEAD) Initial commit
git tag v0.0 c33015e67f //根据提交记录打tag

git push --set-upstream origin feature/gitTag //推送本地内容到远程

git checkout develop
git merge feature/gitTag 合并“feature/gitTag”内容到“develop”分支

git push origin v0.0 //将本地某一个tag推送到远程服务器
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/songlin0859/gitDemo.git
 * [new tag]         v0.0 -> v0.0

git push origin --tags //将本地所有tag推送到远程服务器
Enumerating objects: 1, done.
Counting objects: 100% (1/1), done.
Writing objects: 100% (1/1), 163 bytes | 163.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0)
To https://github.com/songlin0859/gitDemo.git
 * [new tag]         v0.0.1 -> v0.0.1
 * [new tag]         v1.0 -> v1.0

 
git tag -d v0 //删除本地的标签）
git push origin --delete v0.0 //删除远程的标签
To https://github.com/songlin0859/gitDemo.git
 - [deleted]         v0.0