# 往届赛题索引（真题，可练手）

> 来源：MiniOB 官方文档「OceanBase 数据库大赛」栏目 + 官方训练营
> 更新：2026-10-22｜用途：第六届赛题（30 题）10/26 才开，先用往届真题练手

## 1. 2021 届初赛：MiniOB SQL 内核（最经典的一套）

题面全文（含测试用例示例）：<https://oceanbase.github.io/miniob/game/miniob_topics/>

**必做题（7 道，共 70 分，全部做完才累计选做题分）**

| 题目 | 分值 | 一句话考点 |
|---|---|---|
| 优化 buffer pool | 10 | 实现 LRU 淘汰算法（学习 buffer pool 原理） |
| select-meta 元数据校验 | 10 | 查询不存在的列/表要返回失败（校验贯穿全链路） |
| drop-table | 10 | 删表要清掉表相关全部资源（索引等） |
| update | 10 | 实现 update，支持带/不带 where，更新索引 |
| date 字段 | 10 | 从词法到执行全链路加 date 类型，处理非法日期/闰年 |
| select-tables 多表查询 | 10 | 笛卡尔积多表查询，输出列名带表名 |
| aggregation-func | 10 | max/min/count/avg 聚合（注意 avg 整数转浮点） |

**选做题（11 道）**

| 题目 | 分值 | 一句话考点 |
|---|---|---|
| join-tables | 20 | INNER JOIN 多表，多条 on 条件 |
| insert 多行插入 | 10 | 一条 insert 多行，原子性（全成功或全失败） |
| unique 唯一索引 | 10 | create unique index，插入重复返回失败 |
| null 支持 | 10 | nullable 关键字；NULL 与任何值比较都是 FALSE |
| simple-sub-query | 10 | IN/比较运算子查询 + 聚合子查询 |
| multi-index 多列索引 | 20 | 多字段联合索引 |
| text 超长字段 | 20 | 超出一页的 text（4096 字节，超出截断） |
| expression 查询表达式 | 20 | where 中支持 +-*/ 运算表达式 |
| complex-sub-query | 20 | 子查询多表 + AND + 聚合 + 关联父表 |
| order-by | 10 | 排序，默认升序 |
| group-by | 20 | 分组 + 聚合 |

**练习价值**：SQL 解析（flex/bison）→ resolver → executor → 存储 的全链路改造，覆盖 6 届 seekdb 内核题所需的基础能力。必做题里 select-meta / update / date / aggregation 最适合三人分工各拿一道。

## 2. 2024 届初赛：向量数据库（6 题，直接对应 seekdb 检索方向）

题面：<https://oceanbase.github.io/miniob/game/miniob-vectordb-2024/>

| 题 | 内容 |
|---|---|
| 题目一 | VECTOR 类型基础：建表/插入/算术运算/比较 + l2_distance/cosine_distance/inner_product |
| 题目二 | 向量类型扩展：支持 `[1,2,3]` 列表字面量 |
| 题目三 | 高维向量：最大 16000 维存储与检索（不建索引） |
| 题目四 | IVF-Flat 向量索引：CREATE VECTOR INDEX + 将 order by+limit 改写为向量索引扫描 |
| 题目五 | 无索引精确检索 + 完整向量检索 |
| 题目六 | ann-benchmarks 性能：10 分钟内跑完、QPS ≥100、召回率 ≥0.90、内存 ≤1GB |

## 3. 2025 届初赛（三套，最接近第六届的 AI 方向）

- **向量数据库 2025 版**：VECTOR 类型 + DISTANCE()/STRING_TO_VECTOR()/VECTOR_TO_STRING() 函数（更贴近 MySQL 语法）<https://oceanbase.github.io/miniob/game/miniob-vectordb-2025/>
- **create-view 视图题**：实现 CREATE VIEW + 可更新视图规则（单表可更新；多表/表达式列/聚合视图部分或全部只读；嵌套视图继承源视图权限）<https://oceanbase.github.io/miniob/game/create-view-2025/>
- **RAG Benchmark**：MiniOB 当向量库，Langflow 编排 RAG 工作流，数据集为 OceanBase 官方文档；上传 `rag/model.json`，30 题平均召回率 >70% 即通过 <https://oceanbase.github.io/miniob/game/rag-benchmark/>

## 4. 训练营（提交黑盒测试，往年题都能练）

- 训练营：<https://open.oceanbase.com/train>
- 提交前必读：[训练营使用说明](https://oceanbase.github.io/miniob/dev-env/how_to_submit_for_testing/)、[输出规范](https://oceanbase.github.io/miniob/game/miniob-output-convention/)、[调试输出](https://oceanbase.github.io/miniob/game/debug-output/)

## 5. 练习顺序建议（结合第六届方向）

1. **2025 RAG Benchmark** —— 直接对标 PowerContext（RAG/检索/工作流），并练 Langflow
2. **2024 / 2025 向量数据库题** —— 对标 seekdb 检索类题目；先做题目一/二（简单），再碰 IVF-Flat
3. **2021 SQL 题** —— 挑 select-meta / drop-table / update / date / aggregation 各 1 道，打内核底子
4. 每题都走「改代码 → 编译 → 本地 test.sh → 训练营提交」闭环，练熟提测流程

> 注意：第六届 30 题（seekdb 11 / PowerContext 11 / AI 生态 8）10/26 开赛后才在官方平台放出；见 `docs/rules.md`。
