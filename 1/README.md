## 第一课 环境准备

建议优先使用 Linux 环境。如果使用 Windows，请直接跳到 **4. Windows 环境准备**。

### 1. 远程登录 Linux 环境

- 可以 SSH 远程登录的 Linux 服务器
- Windows 下使用 Git 需要考虑编码问题，入门建议优先使用 Linux

### 2. Linux 环境使用 UTF-8 编码

UTF-8 是通用编码，Windows 下可能出现乱码，因此建议使用 Linux 入门。

```bash
$ echo $LANG
en_US.UTF-8
```

确保 vi 等编辑器可以正常输入和显示中文。

### 3. 安装 Git 软件

**CentOS/RHEL**（配置好 EPEL 源后）：
```bash
sudo yum install git
# 或 CentOS 8+/RHEL 8+
sudo dnf install git
```

**Debian/Ubuntu**：
```bash
sudo apt-get update
sudo apt-get install git
```

**其他系统**：请查阅官方文档或搜索对应发行版的安装方法。

### 4. Windows 环境准备

> 💡 **提示**：Windows 用户建议安装 WSL2（Windows Subsystem for Linux）获得更好的 Git 体验。

#### 方案 A：Git for Windows（推荐）

1. 从 [Git for Windows](https://git-scm.com/download/win) 下载安装 Git
2. 安装时建议勾选：
   - Git Bash Here（右键菜单）
   - 使用 VS Code 作为默认编辑器（如已安装）

#### 方案 B：TortoiseGit（图形界面）

1. 从 [TortoiseGit](https://tortoisegit.org/) 下载安装
2. 配置用户名和邮箱：
   - 右键 → TortoiseGit → Settings
   - Git → User Info，填写 Name 和 Email

#### 生成 SSH 密钥（Windows）

**使用 Git Bash**：
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
# 按提示操作，一般直接回车即可
```

**使用 PuTTYgen**（TortoiseGit 自带）：
1. 打开 TortoiseGit 安装目录下的 `puttygen.exe`
2. 点击 "Generate"，随机移动鼠标生成密钥
3. 在 "Key comment" 输入标识（如邮箱）
4. 可选：设置 "Key passphrase" 密码保护
5. 点击 "Save private key" 保存私钥（`.ppk` 格式，**切勿泄露**）
6. 点击 "Save public key" 保存公钥（`.pub` 格式，可公开）
7. 复制 "Public key for pasting into OpenSSH authorized_keys file" 的内容

### 5. 注册 GitHub 账号

1. 访问 [https://github.com](https://github.com)
2. 输入邮箱、用户名和密码
3. 完成验证后点击 "Sign up for GitHub"

---

## ✅ 课程完成检查点

### 1. 可以远程登录 Linux，正常输入中文

执行以下命令，能正确显示本文内容：
```bash
curl https://raw.githubusercontent.com/bg6cq/learngit/master/1/README.md
```

### 2. Git 已安装

执行 `git` 显示帮助信息：
```bash
$ git
usage: git [--version] [--help] [-c name=value]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           [--config-env=<name>=<envvar>] <command> [<args>]

The most commonly used git commands are:
   add        Add file contents to the index
   branch     List, create, or delete branches
   clone      Clone a repository into a new directory
   commit     Record changes to the repository
   push       Update remote refs along with associated objects
   ...
```

### 3. 有 GitHub 账号可以登录

访问 [https://github.com](https://github.com)，点击 "Sign in"，使用账号密码成功登录。

---

> 📌 **下一步**：完成 [第二课 环境配置](../2/README.md)
