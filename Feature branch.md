Feature分支

每添加一个新功能，最好新建一个feature分支，在上面开发，完成后，合并，最后，删除该feature分支.

创建新分支

$ git checkout –b A

$ git add 文件名+类型

$ git stataus

切回原来正在干活时的分支B并准备合并

$ git checkout B

一切顺利的话，feature分支和bug分支是类似的，合并，然后删除。

现在要求:销毁分支

$ git branch –d A

销毁失败。Git友情提醒，A分支还没有被合并，如果删除，将丢失掉修改，如果要强行删除，需要使用大写的-D参数。

(提醒:我操作到这一步时候,并没有提示销毁失败,而是直接删除分支成功.所以任何事情都要具体问题,具体分析)

现在我们强行删除：

$ git branch -D feature-vulcan

总结:

开发一个新feature，最好新建一个分支；

如果要丢弃一个没有被合并过的分支，可以通过git branch -D <name>强行删除。

$ git branch –D 分支名称
