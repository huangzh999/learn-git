# Cursor 编辑器 Git 使用指南

> Cursor 基于 VS Code，Git 集成与 VS Code **同源**（内置 `@builtin git` 扩展）。本文介绍在 Cursor 中完成日常 Git 操作的界面、快捷键、AI 协作方式与常见问题。

---

## 1. 界面入口


| 入口      | 操作                                     |
| ------- | -------------------------------------- |
| 源代码管理面板 | 左侧活动栏 **分支图标**                         |
| 状态栏     | 左下角显示当前**分支名**、同步状态（↑↓ 箭头）             |
| 集成终端    | `Ctrl+`` — 可直接运行` git` 命令              |
| 命令面板    | `Ctrl+Shift+P` → 输入 `Git:` 查看所有 Git 命令 |


打开文件夹后，Cursor 自动检测其中的 `.git` 目录并启用源代码管理。

---

## 2. 日常提交流程

```
修改文件 → 暂存（Stage）→ 填写提交信息 → 提交（Commit）→ 推送（Push）
```

### 2.1 查看变更

- **源代码管理**面板列出「更改」中的文件。
- 点击文件名 → 右侧打开 **diff 对比**（左：旧内容，右：新内容）。
- 编辑器行号旁 **彩色竖条**：绿=新增，蓝=修改，红=删除。

### 2.2 暂存（Stage）


| 操作        | 方式                    |
| --------- | --------------------- |
| 暂存单个文件    | 文件右侧 `+` 号            |
| 暂存单个 hunk | diff 视图中 hunk 上方的 `+` |
| 暂存全部      | 「更改」标题旁 `+`           |
| 取消暂存      | 已暂存文件右侧 `-` 号         |


### 2.3 提交（Commit）

1. 在面板顶部**提交信息输入框**填写 message。
2. 点击 **✓ 提交** 按钮，或 `Ctrl+Enter` 提交

**智能提交**：设置 `git.enableSmartCommit: true` 后，无暂存文件时可直接提交所有更改。

### 2.4 同步远程


| 操作    | 方式                             |
| ----- | ------------------------------ |
| 拉取    | 状态栏 `↓` 或面板 `...` → Pull       |
| 推送    | 状态栏 `↑` 或面板 `...` → Push       |
| 拉取并推送 | 状态栏 **同步** 图标（↻）或 `...` → Sync |


首次推送新分支时，Cursor 会提示设置 upstream。

---

## 3. 分支操作

### 3.1 切换 / 创建分支

- 点击状态栏**左下角分支名** → 弹出分支列表
- 选择已有分支切换，或输入新名称创建分支

### 3.2 命令面板快捷操作

`Ctrl+Shift+P` 后常用：


| 命令                       | 说明          |
| ------------------------ | ----------- |
| `Git: Create Branch...`  | 创建并切换分支     |
| `Git: Checkout to...`    | 切换到已有分支     |
| `Git: Merge Branch...`   | 合并指定分支到当前分支 |
| `Git: Delete Branch...`  | 删除本地分支      |
| `Git: Publish Branch...` | 推送新分支到远程    |


---

## 4. 差异与历史

### 4.1 文件内联 blame（需 GitLens 等扩展）

Cursor 支持安装 VS Code 扩展。推荐 **GitLens** 增强：

- 行级 blame 信息
- 文件/行历史
- 提交图（Commit Graph）

安装：`Ctrl+Shift+X` → 搜索 `GitLens` → Install

### 4.2 时间线（Timeline）

- 资源管理器底部 **Timeline** 面板
- 查看当前文件的 Git 提交历史，点击可 diff

### 4.3 命令面板


| 命令                     | 说明               |
| ---------------------- | ---------------- |
| `Git: View History`    | 查看仓库提交历史         |
| `Git: Show Git Output` | 查看 Git 扩展日志（排错用） |


---

## 5. 合并冲突

1. 执行 merge / pull / rebase 后，冲突文件标记为 **!** 或 **C**
2. 打开冲突文件，Cursor 在冲突块上方显示操作按钮：
  - **Accept Current** — 保留当前分支
  - **Accept Incoming** — 保留传入分支
  - **Accept Both** — 保留双方
  - **Compare Changes** — 对比查看
3. 解决后暂存文件 → 提交（merge）或继续 rebase

也可使用 `Git: Open Merge Editor` 打开三方合并编辑器。

---

## 6. Cursor 特有：AI 与 Git

### 6.1 Agent / Chat 修改的代码

Agent 或 Chat 改文件后，变更会出现在**源代码管理**面板。提交前务必：

- [ ] 确认修改文件与预期一致
- [ ] 检查是否有多余的「顺手改」
- [ ] 验证 import、路径、逻辑是否正确

### 6.2 Chat 中引用 Git 上下文

在 Chat / Composer 输入框使用 `@` 引用：


| 引用        | 用途                         |
| --------- | -------------------------- |
| `@Git`    | 引用当前工作区 diff、最近提交等 Git 上下文 |
| `@Commit` | 引用特定提交（视版本而定）              |


示例：

```
@Git 最近 3 次提交里 authentication 相关改了什么？
```

### 6.3 让 AI 执行 Git 操作

可在 Chat 中要求 Agent 执行 git 命令（如 status、diff、commit），Agent 会通过**集成终端**运行。注意：

- 涉及 push、force、reset 等破坏性操作时，Agent 通常会请求确认
- 重要操作建议自己在面板或终端复核后再执行

---

## 7. 常用快捷键


| 快捷键                  | 功能        |
| -------------------- | --------- |
| `Ctrl+Shift+G`       | 打开源代码管理   |
| `Ctrl+Enter`         | 在提交框聚焦时提交 |
| `Ctrl+Shift+P` → Git | 所有 Git 命令 |
| `Ctrl+``             | 打开/关闭集成终端 |


> macOS 将 `Ctrl` 换为 `Cmd`。

---

## 8. 推荐设置

`Ctrl+,` 打开设置，搜索 `git`：


| 设置项                                 | 建议值                    | 说明                |
| ----------------------------------- | ---------------------- | ----------------- |
| `git.enableSmartCommit`             | `true`                 | 允许直接提交未手动暂存的更改    |
| `git.confirmSync`                   | `true`                 | 同步前确认（防误操作）       |
| `git.autofetch`                     | 按需                     | 定时 fetch，保持远程信息最新 |
| `git.showPushSuccessNotification`   | `true`                 | 推送成功提示            |
| `git.openRepositoryInParentFolders` | `always`               | 子目录打开时仍识别父级仓库     |
| `git.autoRepositoryDetection`       | 多仓库卡顿时改为 `openEditors` | 控制仓库自动扫描范围        |
| `git.repositoryScanMaxDepth`        | 多仓库卡顿时设为 `1`           | 限制扫描深度            |


写入 `settings.json` 示例：

```json
{
  "git.enableSmartCommit": true,
  "git.confirmSync": true,
  "git.autofetch": true
}
```

---

## 9. 集成终端 vs 图形界面


| 场景                     | 推荐方式           |
| ---------------------- | -------------- |
| 日常 add / commit / push | 源代码管理面板        |
| rebase -i、复杂 merge     | 集成终端           |
| 查看详细 log、reflog        | 集成终端 或 GitLens |
| 面板/commit 异常           | 集成终端（更可靠）      |


终端提交示例：

```bash
git add .
git commit -m "feat: 添加用户登录"
git push
```

---

## 10. 常见问题

### Q1：提交按钮无反应 / 卡住

**原因**：`core.editor` 配置与 UI 提交流程冲突，或 commit editor 扩展异常。

**处理**：

1. 在提交框直接输入 message 后 `Ctrl+Enter`
2. 改用终端：`git commit -m "message"`
3. 检查 `git config core.editor`，避免设为 `true` 或与 Cursor 冲突的值
4. 扩展面板 → `@builtin` → **Git** → Restart

### Q2：输入提交信息时界面卡顿

已知问题（部分版本/Linux）。可尝试：

- 升级 Cursor 到最新版
- 关闭部分扩展排查
- 临时改用终端提交

### Q3：多仓库目录扫描很慢

父文件夹含多个 `.git` 子仓库时，源代码管理可能长时间显示 "Scanning..."。

**处理**：

```json
{
  "git.autoRepositoryDetection": "openEditors",
  "git.repositoryScanMaxDepth": 1
}
```

打开目标仓库中的任意文件，Cursor 会识别对应仓库。

### Q4：Windows 下杀毒/OneDrive 导致 Git 慢

- 将项目目录加入杀毒软件白名单
- 避免在 OneDrive 同步目录内开发
- 优先使用本地磁盘路径

### Q5：Cursor 未识别 Git 仓库

1. 确认已 `git init` 或 `git clone`
2. 检查 `git.enabled` 为 `true`
3. `Ctrl+Shift+P` → `Git: Show Git Output` 查看错误
4. 确认系统已安装 Git 且 `git` 在 PATH 中

---

## 11. 与命令行对照


| 图形界面操作     | 等效命令                             |
| ---------- | -------------------------------- |
| 更改列表       | `git status`                     |
| 点击文件看 diff | `git diff` / `git diff --staged` |
| 暂存 `+`     | `git add <file>`                 |
| ✓ 提交       | `git commit -m "..."`            |
| Pull       | `git pull`                       |
| Push       | `git push`                       |
| 状态栏切换分支    | `git switch <branch>`            |
| 同步 ↻       | `git pull` + `git push`          |


更完整的命令说明见项目根目录 `[commond.md](../commond.md)`。

---

## 12. 推荐工作流

```
1. 拉最新代码（Pull / Sync）
2. 创建功能分支（状态栏 → 新分支）
3. 编码（可配合 Agent）
4. 源代码管理面板 Review diff
5. 提交（清晰的 commit message）
6. 推送 → 平台创建 PR
7. Review 通过后合并
```

---

## 相关链接

- [VS Code Git 官方文档](https://code.visualstudio.com/docs/sourcecontrol/overview)（Cursor 行为基本一致）
- [GitLens 扩展](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- 本项目 Git 学习地图：`[README.md](../README.md)`

