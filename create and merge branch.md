创建分支

HEAD严格来说不是指向提交，而是指向master，master才是指向提交的，所以，HEAD指向的就是当前分支。

当我们创建新的分支时A时，Git新建了一个指针叫A，指向master相同的提交，再把Head指向A，就表示当前分支在A上


创建分支，然后切换到分支

$ git checkout -b 分支名称

Switched to a new branch '分支名称'

git checkout命令加上-b参数表示创建并切换，相当于以下两条命令：

$ git branch 分支名称

$ git checkout 分支名称

Switched to branch '分支名称'

用git branch命令查看当前分支：

$ git branch

* 分支名称
  master

在文件中做了修改后

$ git add 文件名+类型

$ git commit –m “”

切换回master分支

$ git checkout master

把创建的分支工作成果合并到master分支上

$ git merge 创建的分支名称

合并完毕后，删除创建的分支

$ git branch –d 创建的分支名称

总结：

查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>

创建+切换分支：git checkout -b <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>
