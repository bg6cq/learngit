## 第七课 合并 Commit，整理修改记录

开发过程中频繁 commit 可以避免修改丢失，但会产生零散的提交记录。

**交互式 Rebase** 可以将多个 commit 合并，让历史更整洁。

> ⚠️ **警告**：
> - **不要**在已推送且其他人可能基于此工作的分支上使用（如公共的 master 分支）
> - **可以**在本地功能分支或 PR 合并前使用
> - 合并 commit 会改变历史，可能需要 `git push --force`

### 1. 合并最近的 N 个 Commit

**合并最近 3 个 commit 为 1 个**：

```bash
$ git rebase -i HEAD~3
```

编辑器会显示：
```
pick abc1111 第一次 commit
pick def2222 第二次 commit
pick ghi3333 第三次 commit
```

修改为（保留第一个 `pick`，后面的改为 `squash` 或 `s`）：
```
pick abc1111 第一次 commit
s def2222 第二次 commit
s ghi3333 第三次 commit
```

保存退出后，会弹出新窗口编辑合并后的 commit message。

完成后，3 个 commit 合并为 1 个。

### 2. 常用 Rebase 命令

| 命令 | 简写 | 说明 |
|------|------|------|
| `pick` | `p` | 使用此 commit（默认） |
| `reword` | `r` | 使用此 commit，但修改 commit message |
| `edit` | `e` | 使用此 commit，但暂停以便修改文件内容 |
| `squash` | `s` | 合并到上一个 commit，同时合并 commit message |
| `fixup` | `f` | 合并到上一个 commit，丢弃此 commit 的 message |
| `drop` | `d` | 删除此 commit |

### 3. 实战练习

```bash
# 创建测试分支
$ git checkout -b test

# 编辑文件，commit，重复 3 次
$ echo "line 1" >> test.txt && git add test.txt && git commit -m "add line 1"
$ echo "line 2" >> test.txt && git add test.txt && git commit -m "add line 2"
$ echo "line 3" >> test.txt && git add test.txt && git commit -m "add line 3"

# 查看 commit 历史
$ git log --oneline
abc1234 (HEAD -> test) add line 3
def5678 add line 2
ghi9012 add line 3

# 合并最近 3 个 commit
$ git rebase -i HEAD~3

# 合并后查看
$ git log --oneline
xyz7890 (HEAD -> test) add 3 lines
```

### 4. 合并指定 Commit

```bash
# 查看 commit 历史
$ git log --oneline

# 合并某个 commit 之后的若干 commit
$ git rebase -i <commit-hash>
```

例如：
```bash
$ git rebase -i a1b2c3d
```

可以在编辑器中选择要合并的 commit。

### 5. 强制推送（谨慎使用）

合并 commit 后，历史已改变，需要强制推送：

```bash
$ git push --force origin test
```

> ⚠️ **警告**：`--force` 会覆盖远程历史，确保没有其他人在此分支上工作。
>
> **更安全的做法**：使用 `--force-with-lease`，如果远程有新提交会失败而不是覆盖：
> ```bash
> $ git push --force-with-lease origin test
> ```

---

## 📌 何时使用 Rebase

| 场景 | 推荐 |
|------|------|
| 合并功能分支到 master 前 | ✅ 整理 commit 历史 |
| 提交 PR 前 | ✅ 让审查更清晰 |
| 本地开发中 | ✅ 随时整理 |
| 公共分支（多人协作） | ❌ 避免改变历史 |
| 已推送且他人基于此工作 | ❌ 会造成混乱 |

---

## ✅ 课程完成检查点

- [ ] 创建分支并多次 commit
- [ ] 使用 `git rebase -i` 合并 commit
- [ ] 理解不同 rebase 命令的用途
- [ ] （可选）尝试修改 commit message（reword）

---

> 📌 **下一步**：完成 [第八课 GitHub Pages](../8/README.md)
