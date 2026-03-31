# Worktrees 使用说明

本项目用于对比 GSD 与 BMAD 的开发能力，采用 `git worktree` 做隔离开发。

## 当前结构

- 主仓库（`main`）：`/Users/xiawuyang/Desktop/PARA/01_Projects/20260331_AI_reader`
- GSD 工作树（`exp/gsd`）：`/Users/xiawuyang/Desktop/PARA/01_Projects/20260331_AI_reader/worktrees/gsd`
- BMAD 工作树（`exp/bmad`）：`/Users/xiawuyang/Desktop/PARA/01_Projects/20260331_AI_reader/worktrees/bmad`

## 常用命令

### 查看 worktree 列表

```bash
git worktree list
```

### 在 GSD 分支开发

```bash
cd /Users/xiawuyang/Desktop/PARA/01_Projects/20260331_AI_reader/worktrees/gsd
git status
git add .
git commit -m "feat: gsd update"
git push
```

### 在 BMAD 分支开发

```bash
cd /Users/xiawuyang/Desktop/PARA/01_Projects/20260331_AI_reader/worktrees/bmad
git status
git add .
git commit -m "feat: bmad update"
git push
```

### 对比分支差异

在主仓库目录执行：

```bash
cd /Users/xiawuyang/Desktop/PARA/01_Projects/20260331_AI_reader
git fetch --all
git diff exp/gsd..exp/bmad
```

### 查看提交对比

```bash
git log --oneline --left-right exp/gsd...exp/bmad
```

## 建议流程

1. 先在 `main` 维护统一需求与评测标准。
2. GSD / BMAD 分别只在各自 worktree 开发。
3. 每完成一个里程碑就 push 到对应分支。
4. 最后在 `main` 汇总结果并输出结论。
