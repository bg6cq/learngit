## 第一课 环境准备

建议的环境：

1. 可以远程ssh登录的Linux环境

Windows下使用git要考虑编码，不适合入门。入门建议使用Linux。

2. Linux环境使用utf-8编码

utf-8是通用的编码，windows下更乱，所以建议使用Linux入门
````
$ echo $LANG
en_US.utf-8
````

只要vi之类的编辑器可以输入中文即可。

3. 安装git软件

对于CentOS，配置好epel库后，执行`yum install git`就可以安装。

对于Debian类系统，执行`apt-get install git`可以安装。

其他系统可以自行google/baidu。

4. 注册github账号

浏览器访问 [https://github.com](https://github.com), 输入想要的账号，邮件，密码，单击 Sign up for GitHub注册。

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

