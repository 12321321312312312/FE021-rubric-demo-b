# FE-021 二期 rubric 演示分支

配合 `V3-二期/rubric-二期-复现分类与演示场景.md` 使用。每个场景若干分支，分支里的工作流都只在**手动触发**时运行，推送不会启动任何流水线。
二期分支统一以 `p2-` 开头；一期分支（`a-*`、`b-*`、`c-*`、`d-*`）保持不变。

场景 B 的仓库轮流要两个仓库：甲 = `FE021-rubric-demo`，乙 = `FE021-rubric-demo-b`。

| 场景 | 仓库甲 `FE021-rubric-demo` | 仓库乙 `FE021-rubric-demo-b` |
|---|---|---|
| A · 紧急度与 30 秒 | `p2-a-bad` `p2-a-hold` `p2-a-p0` `p2-a-p0b` `p2-a-p5` `p2-a-p9` `p2-a-hold80` `p2-a-dep` `p2-a-early` | |
| B · 仓库轮流 | `p2-b-hold` `p2-b-x` `p2-b-x7` | `p2-b-y` `p2-b-y2` |
| C · 没有机器能跑它 | `p2-c-long` `p2-c-gpu` | |
| D · 等待原因全景 | `p2-d-occ` `p2-d-main` | |
| E · 并发组 | `p2-e-a` `p2-e-a2` `p2-e-b` `p2-e-occ` `p2-e-early` `p2-e-late` `p2-e-same` | |
| F · 机器掉线 | `p2-f-long` | |

Agent 标签：`cpu-1`、`cpu-2`、`cpu-3` 为 `demo=c3,kind=cpu`，`gpu-1` 为 `demo=c3,kind=gpu`。每台 `WOODPECKER_MAX_WORKFLOWS=1`。
