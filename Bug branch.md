Bug分支

每个bug都可以通过一个新的临时分支来修复，修复后，合并分支，然后将临时分支删除。

当接到一个修复bug的任务时，需要创建一个分支A来修复它，但是当前正在B分支上进行的工作还没有提交。

Git还提供了一个stash功能，可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作。

$ git stash

用git status查看工作区，就是干净的（除非有没有被Git管理的文件），因此可以放心地创建分支来修复bug。

$ git status

首先确定要在哪个分支上修复bug，假定需要在master分支上修复，就从master创建临时分支：

$ git checkout master

$ git checkout -b A分支

现在修复bug

修复完成后，切换到master分支，并完成合并，最后删除A分支

$ git checkout master

$ git merge --no-ff -m "xxxx" A分支

接着回到B分支干活

$ git checkout B

$ git status

工作区的内容不见了，用以下命令进行查看

$ git stash list

Git把stash内容存在某个地方了，但是需要恢复一下，有两个办法

一是用git stash apply恢复，但是恢复后，stash内容并不删除，你需要用git stash drop来删除；

另一种方式是用git stash pop，恢复的同时把stash内容也删了：

再用git stash list查看，就看不到任何stash内容了：

$ git stash list

你可以多次stash，恢复的时候，先用git stash list查看，然后恢复指定的stash，用命令：

$ git stash apply stash@{0}
