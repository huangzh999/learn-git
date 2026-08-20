# learn-git

Git 学习地图 — 先建立全局认知，再逐块深入。

---

## 0. 前置认知

- Git 是什么 / 与 SVN 等工具的区别
- 分布式 vs 集中式
- 工作区 · 暂存区 · 本地仓库 · 远程仓库
- 常用术语：commit、branch、merge、rebase、remote

---

## 1. 基础操作

- 安装与配置（`user.name` / `user.email`）
- 仓库初始化与克隆
- 日常三板斧：`add` · `commit` · `status` · `log`
- 查看差异：`diff`
- 撤销与恢复：`restore` · `reset` · `checkout`
- `.gitignore` 与忽略规则

---

## 2. 分支

- 分支概念与 HEAD
- 创建 / 切换 / 删除：`branch` · `switch` · `checkout`
- 合并：`merge`（fast-forward / 三方合并）
- 变基：`rebase`（概念与使用场景）
- 冲突的产生与解决

---

## 3. 远程协作

- 远程仓库：`remote` · `fetch` · `pull` · `push`
- 跟踪分支与 upstream
- Fork / Clone / PR 工作流
- 多人协作常见场景

---

## 4. 历史与追溯

- 提交历史：`log` · `show` · `blame`
- 引用：`reflog`
- 挑选与整理：`cherry-pick` · `rebase -i`
- 临时保存：`stash`

---

## 5. 标签与发布

- 轻量标签 vs 附注标签
- `tag` 创建 / 推送 / 检出
- 版本发布基本流程

---

## 6. 高级主题

- 内部对象模型（blob / tree / commit / tag）
- `merge` vs `rebase` 深度对比
- 子模块：`submodule`
- 工作树：`worktree`
- Hooks 与自动化
- 大文件：`LFS`

---

## 7. 平台与工具

- GitHub / GitLab / Gitee
- SSH 密钥与 HTTPS 认证
- GUI 客户端（可选）
- IDE 内置 Git 集成

---

## 8. 最佳实践

- 提交信息规范
- 分支策略（Git Flow / GitHub Flow / Trunk-Based）
- Code Review 流程
- 安全原则（不 force push 公共分支、不提交密钥）

---

## 学习路径建议

```
前置认知 → 基础操作 → 分支 → 远程协作
                ↓
         历史与追溯 → 标签与发布
                ↓
         高级主题（按需） + 平台工具 + 最佳实践
```

---

## 目录规划（待建）

| 模块 | 目录 | 状态 |
|------|------|------|
| 基础操作 | `01-basics/` | 待建 |
| 分支 | `02-branch/` | 待建 |
| 远程协作 | `03-remote/` | 待建 |
| 历史追溯 | `04-history/` | 待建 |
| 标签发布 | `05-tag/` | 待建 |
| 高级主题 | `06-advanced/` | 待建 |
| 练习与笔记 | `notes/` | 待建 |
