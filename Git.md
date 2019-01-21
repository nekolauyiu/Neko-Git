配置帐号信息

ssh-keygen -t rsa -C "你的邮箱"

验证是否配置成功

ssh -T git@github.com

git config –global user.name “Your Name” （注意前边是“- -global”，有两个横线） 

git config –global user.email “email@example.com”

文件夹初始化

git init

创建库所在的路径

$ pwd

仓库当前的状态

git status

上次怎么修改的

git diff

添加文件

git add .

添加注释

git commit -m "xxx"

添加文件夹

$ mkdir +文件夹名字

添加一个中间带空格的文件夹

如： $ mkidr neko\ ly/


增加一个文件

touch 文件名+后缀
如：$ touch neko.py

进入一个有空格的文件夹 neko ly
如：$ cd neko\ ly/

删除文件

$ rm 文件名.文件类型 

增加具体文件

$ git add+文件名.文件类型

git add -A 提交所有变化 

git add -u 提交被修改(modified)和被删除(deleted)文件，不包括新文件(new) 

git add . 提交新文件(new)和被修改(modified)文件，不包括被删除(deleted)文件

看修改了什么

$ git diff 文件名+类型

看文件的内容

$ cat 文件名

与远程仓库建立连接

$ git remote add origin +你复制的内容

比如$ git remote add origin git@github.com:Lolita-Sian/Lolita.git

使用命令git push -u origin master第一次推送master分支的所有内容

验证远程仓库

$ git remote -v

不想连接这个远程仓库

$ git remote remove origin

$ git push -u 代称 master 

如果刚才是git add remote origin +复制内容，就要写git push -u origin master 

如果刚才是git add remote AAA +复制内容，就要写git push -u AAA master

















