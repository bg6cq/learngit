# 练习指南

本文件提供额外的练习建议，帮助巩固 Git 技能。

## 🎯 核心练习

### 练习 1：完整的协作流程
1. Fork [ilovegit](https://github.com/bg6cq/ilovegit) 项目
2. 克隆到本地
3. 创建功能分支 `feature/add-my-info`
4. 在 README.md 中添加你的信息
5. 提交并推送到 GitHub
6. 发起 Pull Request
7. 等待合并后同步上游代码

### 练习 2：分支管理
```bash
# 创建并切换分支
git checkout -b feature/new-feature

# 开发功能（多次 commit）
# ... 编辑文件、add、commit ...

# 同步主分支
git checkout master
git pull origin master

# 变基功能分支
git checkout feature/new-feature
git rebase master

# 合并到主分支
git checkout master
git merge feature/new-feature

# 删除功能分支
git branch -d feature/new-feature
```

### 练习 3：解决冲突
1. 创建两个分支，从同一文件的不同位置修改
2. 尝试合并，制造冲突
3. 手动解决冲突
4. 完成合并

## 🔧 常用命令速查

### 基础操作
```bash
git init              # 初始化仓库
git clone <url>       # 克隆仓库
git status            # 查看状态
git add <file>        # 添加文件
git commit -m "msg"   # 提交
git push              # 推送
git pull              # 拉取
```

### 分支操作
```bash
git branch            # 查看分支
git branch <name>     # 创建分支
git checkout <name>   # 切换分支
git checkout -b <name># 创建并切换
git merge <branch>    # 合并分支
git branch -d <name>  # 删除分支
```

### 历史查看
```bash
git log               # 查看历史
git log --oneline     # 简洁历史
git log --graph       # 图形化历史
git diff              # 查看差异
git show <commit>     # 查看提交详情
```

### 高级操作
```bash
git rebase -i HEAD~N  # 交互式变基
git stash             # 暂存修改
git cherry-pick <c>   # 挑选提交
git reset --hard <c>  # 重置到指定提交
git revert <commit>   # 撤销提交
```

## 📚 推荐练习项目

### 初学者
- 个人笔记管理
- 代码片段收集
- 配置文件备份

### 进阶
- 参与开源项目（文档修正、Bug 修复）
- 维护个人博客（GitHub Pages）
- 团队协作项目

## 🎓 技能检查清单

### 基础（必须掌握）
- [ ] 初始化仓库、添加文件、提交
- [ ] 推送到远程仓库
- [ ] 克隆仓库、拉取更新
- [ ] 查看提交历史和差异

### 中级（应该掌握）
- [ ] 创建和切换分支
- [ ] 合并分支
- [ ] 解决合并冲突
- [ ] 发起 Pull Request

### 高级（建议掌握）
- [ ] 交互式 rebase 整理历史
- [ ] 使用 stash 暂存修改
- [ ] cherry-pick 挑选提交
- [ ] 使用 git bisect 定位问题

## 💡 最佳实践

1. **频繁提交**：小步提交，便于回滚和审查
2. **有意义的 commit message**：说明"为什么"而不是"是什么"
3. **分支命名规范**：
   - `feature/xxx` - 新功能
   - `fix/xxx` - Bug 修复
   - `docs/xxx` - 文档更新
   - `refactor/xxx` - 代码重构
4. **及时同步**：定期拉取上游代码，减少冲突
5. **代码审查**：PR 合并前请他人审查

## 🔗 更多资源

- [Git 官方文档](https://git-scm.com/doc)
- [GitHub Skills](https://skills.github.com/)
- [Learn Git Branching](https://learngitbranching.js.org/) - 互动式学习
- [Oh My Git!](https://ohmygit.org/) - Git 游戏
