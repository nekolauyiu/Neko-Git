多人协作

从远程仓库克隆时，实际上Git自动把本地的master分支和远程的master分支对应起来了，并且，远程仓库的默认名称是origin

要查看远程库的信息

$ git remote
origin

用git remote -v显示更详细的信息：
$ git remote -v

推送分支，就是把该分支上的所有本地提交推送到远程库。推送时，要指定本地分支，这样，Git就会把该分支推送到远程库对应的远程分支上：

$ git push origin master

如果要推送其他分支，比如A，就改成：

$ git push origin A

但是，并不是一定要把本地分支往远程推送，

 master分支是主分支，因此要时刻与远程同步；
 
dev分支是开发分支，团队所有成员都需要在上面工作，所以也需要与远程同步；

bug分支只用于在本地修复bug，就没必要推到远程了，除非老板要看看你每周到底修复了几个bug；

feature分支是否推到远程，取决于你是否和你的小伙伴合作在上面开发。

抓取分支

多人协作时，大家都会往master和dev分支上推送各自的修改。

你的小伙伴要在dev分支上开发，就必须创建远程origin的dev分支到本地，于是他用这个命令创建本地dev分支
$ git checkout -b dev origin/dev

现在，小伙伴就可以在dev上继续修改，然后，时不时地把dev分支push到远程

分别add和commit
$ git push origin 文件名+类型

你的小伙伴已经向origin/dev分支推送了他的提交，而碰巧你也对同样的文件作了修改，并试图推送：

$ cat 文件名+类型

随后add和commit 

$ git push origin dev
推送失败，因为你的小伙伴的最新提交和你试图推送的提交有冲突，解决办法也很简单，Git已经提示我们，

先用git pull把最新的提交从origin/dev抓下来，然后，在本地合并，解决冲突，再推送：

git pull也失败了，原因是没有指定本地dev分支与远程origin/dev分支的链接，根据提示，设置dev和origin/dev的链接：

$ git pull

There is no tracking information for the current branch.
Please specify which branch you want to merge with.
See git-pull(1) for details.

    git pull <remote> <branch>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=origin/<branch> dev

$ git branch --set-upstream-to=origin/dev dev

再pull

这回git pull成功，但是合并有冲突，需要手动解决，解决的方法和分支管理中的解决冲突完全一样。解决后，提交，再push：

$ git commit –m “xxx”

$ git push origin dev

因此，多人协作的工作模式通常是这样：

1.	首先，可以试图用git push origin <branch-name>推送自己的修改；

2.	如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；

3.	如果合并有冲突，则解决冲突，并在本地提交；

4.	没有冲突或者解决掉冲突后，再用git push origin <branch-name>推送就能成功！

如果git pull提示no tracking information，则说明本地分支和远程分支的链接关系没有创建，

用命令git branch --set-upstream-to <branch-name> origin/<branch-name>。

小结

查看远程库信息，使用git remote -v；

本地新建的分支如果不推送到远程，对其他人就是不可见的；

从本地推送分支，使用git push origin branch-name，如果推送失败，先用git pull抓取远程的新提交；

在本地创建和远程分支对应的分支，使用git checkout -b branch-name origin/branch-name，本地和远程分支的名称最好一致；

建立本地分支和远程分支的关联，使用git branch --set-upstream branch-name origin/branch-name；

从远程抓取分支，使用git pull，如果有冲突，要先处理冲突。
