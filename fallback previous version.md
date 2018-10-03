需求：回到过去某个版本

【首先，Git必须知道当前版本是哪个版本，在Git中，用HEAD表示当前版本，也就是最新的提交xxx...，
上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100】

我们要把当前版本退回到上一个版本，就可以使用
$ git reset --hard HEAD^

如果想还是回到修改之前的状态，窗口没关的情况下，往上找，找到要回到过去的那个版本的id
$ git reset --hard id号
hard id号
Id号就是在git log(或git log --pretty=oneline里查找的那些数字)

【让HEAD指向哪个版本号，你就把当前版本定位在哪】

如果关掉电脑后想反悔，解决方案：
记录你的每一次命令
$ git reflog
执行
$ git reset --hard 加id号

【版本的历史之间穿梭，使用命令git reset --hard commit_id
穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。
要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本】
