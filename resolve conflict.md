解决冲突

准备新的分支

$ git branch –b 分支名称

修改文件内容

在新分支上分别add 和commit

切换回master

在master上对文件进行修改后add 和commit 提交

这个时候出现了，master分支和新分支各自都分别有新的提交

这种情况下，Git无法执行“快速合并”，只能试图把各自的修改合并起来，但这种合并就可能会有冲突。

$ git merge 新分支名称

Git告诉我们，文件存在冲突，必须手动解决冲突后再提交

$ git status

通过查看文件内容

$ cat 文件名称+类型

Git用<<<<<<<，=======，>>>>>>>标记出不同分支的内容，我们修改如下后保存，再提交。

$ git add 文件名+类型

查看到分支的合并情况

$ git log 

删除分支

$ git checkout –d 分支名称

用git log --graph命令可以看到分支合并图
