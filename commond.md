# Git 命令速查

> 按 `git help -a` 分类罗列，每条仅作功能简述。用法详见 `git help <command>`。

---

## 一、常用命令（Main Porcelain）

| 命令 | 说明 |
|------|------|
| `add` | 将文件变更加入暂存区 |
| `am` | 从 mailbox 格式应用一系列补丁 |
| `archive` | 从指定树对象导出文件归档（tar/zip） |
| `bisect` | 二分查找引入 bug 的提交 |
| `branch` | 列出、创建或删除分支 |
| `bundle` | 通过归档包移动对象和引用 |
| `checkout` | 切换分支或恢复工作区文件（旧式，推荐用 switch/restore） |
| `cherry-pick` | 将指定提交的应用到当前分支 |
| `citool` | 图形化提交界面 |
| `clean` | 删除工作区中未跟踪的文件 |
| `clone` | 克隆远程仓库到本地 |
| `commit` | 将暂存区变更记录为新提交 |
| `describe` | 根据可用引用为对象生成可读名称（如 v1.0-5-gabc123） |
| `diff` | 比较工作区、暂存区、提交之间的差异 |
| `fetch` | 从远程下载对象和引用，不合并 |
| `format-patch` | 将提交导出为邮件补丁格式 |
| `gc` | 垃圾回收，清理并优化本地仓库 |
| `gitk` | Git 仓库图形化浏览器 |
| `grep` | 在仓库文件中搜索匹配行 |
| `gui` | 跨平台 Git 图形界面 |
| `init` | 初始化空仓库或重新初始化 |
| `log` | 查看提交历史 |
| `maintenance` | 运行仓库维护与优化任务 |
| `merge` | 合并两个或多个开发历史 |
| `mv` | 移动或重命名文件（并更新索引） |
| `notes` | 为对象添加或查看注释 |
| `pull` | 拉取远程变更并合并到当前分支 |
| `push` | 将本地提交和引用推送到远程 |
| `range-diff` | 比较两个提交范围（如分支的两个版本） |
| `rebase` | 将提交变基到新的基底之上 |
| `reset` | 重置 HEAD 和/或暂存区到指定状态 |
| `restore` | 恢复工作区或暂存区文件 |
| `revert` | 创建新提交以撤销指定提交的变更 |
| `rm` | 从工作区和暂存区删除文件 |
| `shortlog` | 按作者汇总 `git log` 输出 |
| `show` | 显示提交、标签、树等对象详情 |
| `sparse-checkout` | 初始化或修改稀疏检出配置 |
| `stash` | 暂存当前未提交的变更 |
| `status` | 查看工作区和暂存区状态 |
| `submodule` | 初始化、更新或查看子模块 |
| `switch` | 切换分支 |
| `tag` | 创建、列出、删除或验证标签 |
| `worktree` | 管理多个工作树 |

---

## 二、辅助命令 / 操作类（Manipulators）

| 命令 | 说明 |
|------|------|
| `config` | 读取或设置仓库/全局配置 |
| `fast-export` | 导出 Git 数据（供迁移/转换） |
| `fast-import` | 快速导入 Git 数据的底层接口 |
| `filter-branch` | 重写分支历史（已不推荐，优先 filter-repo） |
| `mergetool` | 调用外部工具解决合并冲突 |
| `pack-refs` | 将引用打包以提升访问效率 |
| `prune` | 从对象库中清除不可达对象 |
| `reflog` | 查看和管理引用日志 |
| `remote` | 管理远程仓库列表 |
| `repack` | 重新打包松散对象 |
| `replace` | 创建、列出、删除用于替换对象的引用 |

---

## 三、辅助命令 / 查询类（Interrogators）

| 命令 | 说明 |
|------|------|
| `annotate` | 逐行标注文件的提交信息（同 blame 旧名） |
| `blame` | 显示文件每行最后修改的提交与作者 |
| `bugreport` | 收集信息用于提交 Git bug 报告 |
| `count-objects` | 统计松散对象数量及磁盘占用 |
| `difftool` | 使用外部 diff 工具展示变更 |
| `fsck` | 校验对象库连通性与完整性 |
| `gitweb` | Git 仓库 Web 浏览界面 |
| `help` | 显示 Git 命令帮助 |
| `instaweb` | 临时启动 gitweb 浏览当前仓库 |
| `merge-tree` | 模拟三方合并，不修改索引 |
| `rerere` | 复用已记录的冲突解决方案 |
| `show-branch` | 显示分支及其提交关系 |
| `verify-commit` | 验证提交的 GPG 签名 |
| `verify-tag` | 验证标签的 GPG 签名 |
| `whatchanged` | 显示每次提交引入的差异（log 旧形式） |

---

## 四、与其他系统交互（Interacting with Others）

| 命令 | 说明 |
|------|------|
| `archimport` | 从 GNU Arch 仓库导入 |
| `cvsexportcommit` | 将单个提交导出到 CVS 工作副本 |
| `cvsimport` | 从 CVS 仓库导入 |
| `cvsserver` | 模拟 CVS 服务器访问 Git 仓库 |
| `imap-send` | 通过 IMAP 发送补丁集 |
| `p4` | 与 Perforce 仓库导入/提交 |
| `quiltimport` | 将 quilt 补丁集应用到当前分支 |
| `request-pull` | 生成待合并变更的摘要（供维护者拉取） |
| `send-email` | 将补丁集作为邮件发送 |
| `svn` | Git 与 Subversion 仓库双向同步 |

---

## 五、底层命令 / 操作类（Low-level Manipulators）

| 命令 | 说明 |
|------|------|
| `apply` | 将补丁应用到文件和/或索引 |
| `checkout-index` | 从索引复制文件到工作区 |
| `commit-graph` | 写入或验证 commit-graph 文件 |
| `commit-tree` | 直接创建 commit 对象 |
| `hash-object` | 计算对象 ID，可选创建 blob |
| `index-pack` | 为已有 pack 文件构建索引 |
| `merge-file` | 对单个文件执行三方合并 |
| `merge-index` | 对索引中需合并的文件执行合并 |
| `mktag` | 创建并校验 tag 对象 |
| `mktree` | 从文本格式构建 tree 对象 |
| `multi-pack-index` | 写入或验证 multi-pack-index |
| `pack-objects` | 将对象打包为 pack 归档 |
| `prune-packed` | 删除已在 pack 中的冗余松散对象 |
| `read-tree` | 将 tree 信息读入索引 |
| `symbolic-ref` | 读取、修改或删除符号引用 |
| `unpack-objects` | 从 pack 归档解包对象 |
| `update-index` | 将工作区文件内容注册到索引 |
| `update-ref` | 安全更新 ref 指向的对象 |
| `write-tree` | 从当前索引创建 tree 对象 |

---

## 六、底层命令 / 查询类（Low-level Interrogators）

| 命令 | 说明 |
|------|------|
| `cat-file` | 查看对象内容、类型或大小 |
| `cherry` | 查找尚未应用到上游的提交 |
| `diff-files` | 比较工作区与索引中的文件 |
| `diff-index` | 比较 tree 与工作区或索引 |
| `diff-tree` | 比较两个 tree 对象中的 blob |
| `for-each-ref` | 输出每个 ref 的信息 |
| `for-each-repo` | 在多个仓库上批量执行 Git 命令 |
| `get-tar-commit-id` | 从 archive 中提取 commit ID |
| `ls-files` | 显示索引和工作区中的文件信息 |
| `ls-remote` | 列出远程仓库的引用 |
| `ls-tree` | 列出 tree 对象的内容 |
| `merge-base` | 查找两个提交的最佳共同祖先 |
| `name-rev` | 为给定 rev 查找符号名称 |
| `pack-redundant` | 查找冗余的 pack 文件 |
| `rev-list` | 按时间倒序列出 commit 对象 |
| `rev-parse` | 解析和转换版本参数 |
| `show-index` | 显示 pack 索引内容 |
| `show-ref` | 列出本地仓库的所有引用 |
| `unpack-file` | 将 blob 内容写入临时文件 |
| `var` | 显示 Git 内部逻辑变量 |
| `verify-pack` | 校验 pack 归档文件 |

---

## 七、底层命令 / 仓库同步（Syncing Repositories）

| 命令 | 说明 |
|------|------|
| `daemon` | 简易 Git 协议服务器 |
| `fetch-pack` | 从远程接收缺失对象 |
| `http-backend` | Git over HTTP 的服务端实现 |
| `send-pack` | 通过 Git 协议推送对象 |
| `update-server-info` | 更新 dumb HTTP 服务器的辅助信息 |

---

## 八、底层命令 / 内部辅助（Internal Helpers）

| 命令 | 说明 |
|------|------|
| `check-attr` | 显示 gitattributes 属性信息 |
| `check-ignore` | 调试 .gitignore / exclude 规则 |
| `check-mailmap` | 显示联系人的规范名称和邮箱 |
| `check-ref-format` | 校验引用名称格式是否合法 |
| `column` | 以列格式显示数据 |
| `credential` | 获取和存储用户凭据 |
| `credential-cache` | 在内存中临时缓存密码 |
| `credential-store` | 将凭据持久化到磁盘 |
| `fmt-merge-msg` | 生成合并提交信息 |
| `interpret-trailers` | 解析或添加 commit message 中的 trailer |
| `mailinfo` | 从邮件中提取补丁和作者信息 |
| `mailsplit` | 拆分 UNIX mbox 邮件 |
| `merge-one-file` | merge-index 的标准辅助程序 |
| `patch-id` | 计算补丁的唯一 ID |
| `sh-i18n` | Shell 脚本的 i18n 设置 |
| `sh-setup` | Shell 脚本的公共初始化 |
| `stripspace` | 去除多余空白 |

---

## 九、外部扩展命令（External Commands）

> 需单独安装，非 Git 核心自带。

| 命令 | 说明 |
|------|------|
| `git flow` | Git Flow 分支模型工作流扩展 |
| `git lfs` | 大文件存储（Large File Storage）扩展 |
| `git update-git-for-windows` | 更新 Windows 版 Git（Windows 环境） |

---

## 十、最常用命令速记

```
init / clone          建仓库 / 克隆
status / diff / log   看状态 / 看差异 / 看历史
add / commit          暂存 / 提交
branch / switch       分支管理 / 切换
merge / rebase        合并 / 变基
remote / fetch / pull / push   远程协作
stash / cherry-pick / revert   暂存 / 摘取 / 撤销
tag / reset / restore          标签 / 重置 / 恢复
config / help                  配置 / 帮助
```
