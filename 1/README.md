## 第一课 环境准备

建议的环境是Linux环境，如果使用windows，请直接跳到4. windows环境准备：

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

4. Windows环境准备（厦门大学郑海山老师贡献本节内容）（Linux环境可以跳过这一步到5. 注册github账号）

* 首先从[https://git-for-windows.github.io/](https://git-for-windows.github.io/)下载安装 windows下的Git命令行

* 再从 [https://tortoisegit.org/](https://tortoisegit.org/) 下载安装 tortoiseGit 乌龟

* 设置用户名和密码，运行tortoiseGit 乌龟，右键，打开TortoiseGit->Settings，第5项“Git”，有个“User Info”，“Name”输入名字，Email输入email即可。

* 生成ssh key

  打开 tortoiseGit 乌龟的安装目录，比如 C:\Program Files\TortoiseGit\bin ，打开 puttygen.exe ，点击“generate”按钮，点击完随机移动鼠标，会自动生成一个key，在“Key comment”里面输入你任意想写的东西，比如email。“Key passphrase”是key的密码保护，可以不需要密码。然后点击“Save private key”，保存成一个密钥，后缀名是ppk。这个密钥不能给任何人。再“Save public key”，保存公钥，后缀名选择.pub。然后把 “Public key for pasting into OpenSSH authorized_keys file: " 这串的内容放到Git web控制台的Profile setting->SSH Keys，"Add SSH Key"，上 ，这样子你就可以用密钥push 和pull Git内容了。公钥可以给任何人。

5. 注册github账号

浏览器访问 [https://github.com](https://github.com), 输入想要的账号、邮件、密码，单击 "Sign up for GitHub" 注册。

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
   
浏览器访问 [https://github.com](https://github.com)，单击 "Sign in", 输入自己账号、密码，可以登录。

