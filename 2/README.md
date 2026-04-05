## 第二课 环境配置

### 1. 设置用户信息

配置 Git 用户信息（请替换为你的真实信息）：

```bash
git config --global user.name "Zhang Huanjie"
git config --global user.email "james@ustc.edu.cn"
```

**验证配置**：
```bash
$ git config --global -l
user.name=Zhang Huanjie
user.email=james@ustc.edu.cn
```

> 💡 **提示**：
> - `--global` 表示全局配置（对所有仓库生效）
> - 邮箱建议使用 GitHub 账号关联的邮箱
> - 可在 GitHub Settings → Emails 中设置邮箱隐私

### 2. 生成 SSH 密钥

SSH 密钥是 Git 客户端与 GitHub 认证最方便的方式。

#### 检查是否已有 SSH 密钥

```bash
ls -al ~/.ssh
```

如果存在 `id_rsa` 和 `id_rsa.pub`（或 `id_ed25519` 和 `id_ed25519.pub`），说明已生成过，可跳过此步。

#### 生成新的 SSH 密钥

**推荐：使用 Ed25519 算法**（更安全）：
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

**或使用 RSA 算法**（兼容性更好）：
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

按提示操作：
- 保存路径：直接回车（默认 `~/.ssh/id_ed25519`）
- 密码短语：可选，直接回车表示无密码

生成的文件：
- `~/.ssh/id_ed25519` - **私钥**（妥善保管，切勿泄露）
- `~/.ssh/id_ed25519.pub` - **公钥**（可公开）

#### 查看公钥内容

```bash
$ cat ~/.ssh/id_ed25519.pub
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAI... your_email@example.com
```

### 3. 登录 GitHub

访问 [https://github.com](https://github.com)，点击右上角 "Sign in" 登录。

### 4. 添加 SSH 公钥到 GitHub

1. 点击右上角头像 → **Settings**
2. 左侧菜单选择 **SSH and GPG keys**
3. 点击右上角 **New SSH key** 或拉到页面底部
4. 填写：
   - **Title**：任意标识（如 "My Laptop"）
   - **Key type**：选择 "Authentication Key"
   - **Key**：粘贴 `id_ed25519.pub` 的完整内容（**确保是一行，无换行**）
5. 点击 **Add SSH key**
6. 可能需要输入 GitHub 密码验证

### 5. 测试 SSH 连接

```bash
$ ssh -T git@github.com
Hi your_username! You've successfully authenticated, but GitHub does not provide shell access.
```

看到成功提示说明配置完成。

---

## ✅ 课程完成检查点

### 1. 配置了姓名和邮箱

```bash
$ git config --global -l
user.name=Zhang Huanjie
user.email=james@ustc.edu.cn
```

### 2. Linux 服务器上有 SSH 密钥

```bash
$ ls ~/.ssh
id_ed25519  id_ed25519.pub  known_hosts
```

### 3. GitHub 账号中添加了公钥

访问 [https://github.com/settings/keys](https://github.com/settings/keys) 可以看到已添加的公钥。

### 4. SSH 连接测试成功

```bash
$ ssh -T git@github.com
Hi your_username! You've successfully authenticated...
```

---

> 📌 **下一步**：完成 [第三课 新建项目，跟踪修改](../3/README.md)
