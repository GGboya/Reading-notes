### 如何保持本地 Git 日志的线性历史

为了保持本地 Git 日志的线性历史，可以使用以下步骤：

1. **创建和开发分支**：
   - 基于 `main` 分支，创建一个新的分支 `dev`：
     ```bash
     git checkout -b dev main
     ```
   - 分别在 `main` 和 `dev` 分支上进行开发。此时，它们的提交历史是分叉的，因为在不同的分支上进行了不同的开发工作。

2. **重置基点和合并**：
   - 在 `dev` 分支上执行 `rebase` 命令，以基于 `main` 分支的最新提交：
     ```bash
     git checkout dev
     git rebase main
     ```
   - 解决 `rebase` 过程中可能出现的冲突。解决冲突后，继续重置基点：
     ```bash
     git rebase --continue
     ```
   - 切换回 `main` 分支，并合并 `dev` 分支的更改：
     ```bash
     git checkout main
     git merge dev
     ```

通过这些步骤，`main` 分支的提交历史将保持线性，因为 `rebase` 命令将 `dev` 分支的提交重新应用到 `main` 分支的最新提交之上，没有创建合并提交。

---
