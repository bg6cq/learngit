## 第七课 合并commit，整理修改记录

自己在开发过程中，为了避免修改记录丢失，可能会频繁commit。

这样一来会有很多零散的commit，也可能有一些翻来倒去的修改，这些修改是不需要保留修改记录的。

合并commit操作可以将若干commit合并成1个，让commit看起来更加整洁。

一般在合并分支或提交Pull Requst之前，先用git rebase变基，使得自己的修改基于最新的master；然后对commit进行合并，整理修改记录，让修改历史更加整洁；最后才合并分支或提交Pull Requst。。

注意：一旦commit已经由其他人获取，请勿轻易合并commit，因为这样会让别人混乱。因此千万不要在master分支进行合并commit操作。

如果已经git push 到服务器，合并commit后因为改变了历史，需要使用git push --force强制push。

最常见的合并commit方式是交互式 rebase，具体如下：

1. 合并最近的N个commit

如果需要将最近的N个commit合并成1个：
````
git rebase -i HEAD~N
````
例如，合并最近的3个commit:
````
git rebase -i HEAD~3
````
在弹出的编辑器中，你会看到类似这样的内容：
````
pick abc1111 第一次commit
pick def2222 第二次commit
pick ghi3333 第三次commit
````
保留第一个 pick，把后面的 pick 改为 squash（或 s）：
````
pick abc1111 第一次commit
s def2222 第二次commit
s ghi3333 第三次commit
````
保存退出后，会弹出新窗口让你编辑合并后的 commit message。

完成后，这3个commit就合并成1个了。

除了squash命令外，还可以有以下常用命令可以操作commit。
````
pick   p 使用此 commit（默认）
reword r 使用此 commit，但修改 commit message
edit   e 使用此 commit，但暂停以便修改文件内容
squash s 合并到上一个 commit，同时合并 commit message
fixup  f 合并到上一个 commit，丢弃此 commit 的 message
````

你可以
````
git checkout -b test #创建一个分支
然后 编辑文件，commit，重复3次。

然后用git rebase -i HEAD~3 将3次commit合并成1个。
````


2. 合并若干个commit

````
git log 看到commit历史后

git rebase -i AAAA BBBB
可以将AAAA 之后的commit一直到BBBB合并，但AAAA commit是不修改。
````
你好
````
在test分支中
编辑文件，commit，重复5次。

git log 查看commit 记录

然后用git rebase -i AAAA BBBB 将AAAA后直到BBBB的若干commit合并成1个。
````


## 课程完成检查点

1. 会灵活使用git rebase -i 合并commit
