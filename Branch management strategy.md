分支管理策略

通常，合并分支时，如果可能，Git会用Fast forward模式，但这种模式下，删除分支后，会丢掉分支信息。

如果要强制禁用Fast forward模式，Git就会在merge时生成一个新的commit，这样，从分支历史上就可以看出分支信息。

首先，仍然创建并切换dev分支

$ git checkout –b 新分支名称

修改文件后，提交新commit

切换回master

$ git checkout master

准备合并新分支，请注意 --no-ff参数，表示禁用Fast forward

因为本次合并要创建一个新的commit，所以加上-m参数，把commit描述写进去。

合并后查看分支历史：

$ git log

合并分支时，加上--no-ff参数就可以用普通模式合并，合并后的历史有分支，

能看出来曾经做过合并，而fast forward合并就看不出来曾经做过合并
