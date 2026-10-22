# ob-cup-2026

2026 第六届 OceanBase 数据库大赛 · 三人队仓库

## 目标

- 初赛 **250 分保底，冲 300 分**
- 做 **12–15 题**，不追求 620 满分
- 初赛：**2026-10-26 – 2026-11-18**
- 决赛：2026 年 12 月中旬（线下黑客松）

## 团队

| 角色 | 姓名 | 主责 | 备份 |
|---|---|---|---|
| A 队长 / 引擎 | 待填 | 平台核心、seekdb、Git、提测 | B |
| B 效果 / 评测 | 待填 | PowerContext、检索/压缩/记忆、评测 | A |
| C 交付 / 生态 | 待填 | AI 生态题、Demo、部署、视频 | B |

详细分工见 [docs/team.md](docs/team.md)。

## 仓库结构

```
ob-cup-2026/
├── README.md                 # 本文件
├── docs/                     # 规则、排期、台账、决策
│   ├── team.md               # 角色与可用时间
│   ├── rules.md              # 比赛规则与链接
│   ├── task-matrix.md        # 30 题打分表
│   ├── submission-log.md     # 提测台账
│   └── decisions.md          # 决策记录
├── platform/                 # 薄平台：五个接口
│   ├── ingest/               # 采集/读取
│   ├── context/              # 分块/压缩/记忆
│   ├── store/                # seekdb 封装
│   ├── retrieve/             # 向量+全文+重排
│   ├── agent/                # 模型调用/工作流
│   └── eval/                 # 评测脚本
├── tasks/                    # 每题一个目录
│   └── <题号>/
│       ├── run.py
│       ├── README.md
│       └── test.sh
├── demo/                     # Streamlit/Gradio 演示
└── scripts/                  # 启动/自检脚本
```

## 每题三件套

每道题必须包含：

1. `run.py`：能独立运行，不依赖其他题；
2. `README.md`：题目理解、复现步骤、结果、截图；
3. `test.sh`：至少一个可重复的测试。

## 协作规则

- `main` 分支保持可运行；每人用 `feat/<题号>-<姓名>` 分支。
- 只有队长 A 负责提测；每次提交后更新 `docs/submission-log.md`。
- 任何换题、换方案、改接口，写进 `docs/decisions.md`。
- 每周五 22:00 前必须有可提交版本；周日统一提测。
- 提交信息格式：`feat(pc-01): add pdf parser` / `fix(sd-03): handle empty query`。

## 快速开始

```bash
git clone https://github.com/3156477473-wsx/ob-cup-2026.git
cd ob-cup-2026
```

环境：

- Python 3.11+
- Docker
- Git

官方资料：

- 大赛官网：<https://open.oceanbase.com/competition>
- 官方课程：<https://open.oceanbase.com/course/850>
- 赛题文档：<https://oceanbase.yuque.com/org-wiki-obtech-vh7w9r/hc3pio/ocqe6xv6mlgapq24>
- seekdb：<https://github.com/oceanbase/seekdb>
- PowerContext：<https://github.com/oceanbase/powercontext>
