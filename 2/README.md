## 大家一起学Git 第二课 环境配置

1. 设置自己的名字和邮件地址

在Linux中执行以下命令设置自己的信息，请用自己的信息替换如下内容：
````
git config --global user.name "Zhang Huanjie"
git config --global user.email james@ustc.edu.cn

````

2. 生成ssh-key

ssh-key是git客户端与github认证最方便的方式。

首先查看自己的账户是否已经生成过ssh-key，执行命令
····
james@linux ~]$ ls -al ~/.ssh
drwx------  2 james users 4096 Nov 27  2015 .
drwxr-xr-x 27 james users 4096 Oct 16 23:06 ..
-rw-------  1 james users 1675 Nov 22  2015 id_rsa
-rw-r--r--  1 james users  405 Nov 22  2015 id_rsa.pub
····
如果自己的home目录.ssh目录下存在id_rsa和id_rsa.pub，说明ssh-key已经存在，可以跳过这一步。

否则执行
```
ssh-keygen
```
生成ssh-key，其中的`id_rsa`是自己的私钥，请妥善保存；`id_ras.pub`是自己的公钥，别人拿到也无所谓，可以随意公布。
上面的文件id_rsa.pub内容是
```
[james@linux ~]$ cat ~/.ssh/id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAr9X0n+zQ0zS7A9JLV8611I4w4B13MEbdmDkGf6OyL4f0LVLPY2f7yZpi8VqgyqwUasGtMYRcyE/A7vln+pNEwASPviluhfGr7coxE9ZisdxXTkex9oqhqPfmhnlBjLtsTg3Yh4ZLmzgYprQgAacT9Fc1hNnrc5vwh5lMh7i+bfVkIXbKY8k2dc39qBbsVxtmLDd1rLpb4i+laajglrBvHWFrWdMiOp4Y/O948hSuShDhpthvkV+ZYOlh9QsRD2rXNqfTMC0QXYeYI3tNUMdGxdqgdMC7ZwpH69e5l9WhnMEK1N8io5lITwEhSyoouRmJGuaYaF8MY6BHicuBu9FJEw== james@linux.ustc.edu.cn
````

3. 登录GitHub

浏览器访问 [https://github.com](https://github.com), 单击Sing in, 输入自己账号，
密码，登录Github。如果已经登录，请忽略这一步。

4. 将自己的公钥加到github账号中

单击最右上角的图标，弹出的下来框中，单击"Settings"

输入想要的账号，邮件，密码，单击 Sign up for GitHub注册。

## 课程完成检查点
1. 可以远程登录Linux，输入中英文

执行以下命令，可以输出本文
````
curl https://raw.githubusercontent.com/bg6cq/learngit/master/1/README.md
````
2. 执行`git`有显示
```
$ git
usage: git [--version] [--help] [-c name=value]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p|--paginate|--no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]

The most commonly used git commands are:
   add        Add file contents to the index
   bisect     Find by binary search the change that introduced a bug
   branch     List, create, or delete branches
   checkout   Checkout a branch or paths to the working tree
   clone      Clone a repository into a new directory
   commit     Record changes to the repository
   diff       Show changes between commits, commit and working tree, etc
   fetch      Download objects and refs from another repository

```

3. 有github账号可以登录
   
浏览器访问 [https://github.com](https://github.com)，单击Sign in, 输入自己账号，密码，可以登录。

