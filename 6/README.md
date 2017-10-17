## 第六课 创建分支、分支的合并

git的一个巨大优点就是创建分支、分支间切换、分支的合并很容易。

当一个项目已经稳定运行，需要开发某些特性或新版本时，可以创建一个新的分支，在分支中开发，而不去影响已有的稳定项目。

1. 创建一个分支

在第四课的目录下进行，先同步最近的代码，然后创建并切换到一个新分支 mytest。
````
[james@linux ilovegit]$ cd ~/ilovegit/
[james@linux ilovegit]$ git pull upstream master
From https://github.com/bg6cq/ilovegit
 * branch            master     -> FETCH_HEAD
Already up-to-date.
[james@linux ilovegit]$ git checkout -b mytest
Switched to a new branch 'mytest'
[james@linux ilovegit]$ git branch
  master
* mytest
````
`git branch`显示"* mytest"说明已经处于mytest分支。

2. 在分支mytest中修改

修改文件，可以用vi，以下命令演示文件修改和git diff/git status，以及如何将分支提交给服务器：
````
[james@linux ilovegit]$ echo "这是分支mytest的修改" >> README.md
[james@linux ilovegit]$ git diff
diff --git a/README.md b/README.md
index 5ec1b16..04d08a6 100644
--- a/README.md
+++ b/README.md
@@ -5,3 +5,4 @@
 我喜欢git，我是来自中国科大的测试用户。

 我喜欢git，我是来自四川托普职院的用户。
+这是分支mytest的修改
[james@linux ilovegit]$ git status
# On branch mytest
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#       modified:   README.md
#
no changes added to commit (use "git add" and/or "git commit -a")
[james@linux ilovegit]$ git add README.md
[james@linux ilovegit]$ git commit -m "mytest branch test"
[mytest 706b7ca] mytest branch test
 1 file changed, 1 insertion(+)
[james@linux ilovegit]$ git push origin mytest
Counting objects: 12, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (7/7), done.
Writing objects: 100% (10/10), 1007 bytes, done.
Total 10 (delta 3), reused 0 (delta 0)
remote: Resolving deltas: 100% (3/3), completed with 1 local object.
To git@github.com:zhangyunkai/ilovegit.git
 * [new branch]      mytest -> mytest
````

最后的`git push origin mytest`是把分支提交到服务器。

这时登录自己的 https://github.com/XXXX/ilovegit ，在branches下可以看到mytest分支里文件内容有变化，master分支中仍旧是旧的文件。

3. 分支的合并

当分支的开发基本完成，可以稳定运行后，应该把修改应用到master中，就叫做合并。当然合并也可以在其他分支之间发生。

在mytest分支中，README.md 中增加内容"我喜欢git，也喜欢GitHub，我是来自中国科大的测试用户。"并提交到服务器。

登录服务器查看，mytest分支的内容是"我喜欢git，也喜欢GitHub，我是来自中国科大的测试用户。"

而master分支还是"我喜欢git，我是来自中国科大的测试用户。"

分支的合并很简单拿，只要切换到master分支，merge mytest，然后把master分支提交到服务器。
````
[james@linux ilovegit]$ git checkout master
Switched to branch 'master'
[james@linux ilovegit]$ git merge mytest
Updating 983962c..2170f78
Fast-forward
 README.md | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
[james@linux ilovegit]$ more README.md
## git 学习宣言

我喜欢git，我是来自中国科大的张焕杰。

我喜欢git，也喜欢GitHub，我是来自中国科大的测试用户。

我喜欢git，我是来自四川托普职院的用户。
[james@linux ilovegit]$ git push origin master
Total 0 (delta 0), reused 0 (delta 0)
To git@github.com:zhangyunkai/ilovegit.git
   983962c..2170f78  master -> master
````


## 课程完成检查点

1. 创建分支，并把分支的修改推送到服务器

2. 在github上可以看到分支的有向图

  这时登录自己的 https://github.com/XXXX/ilovegit ，在"Inghts/Network"下，可以看到分支的有向图，更加直观。

  
   

