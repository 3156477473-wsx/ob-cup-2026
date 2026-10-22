# 零基础词表（大白话版）

> 遇到不认识的缩写，先拆开看全称，再记一句大白话。新词往下加，不用背。

| 词 | 全称 / 英文 | 大白话 |
|---|---|---|
| 页 Page | page | 硬盘上的一块数据，大小固定（比如 16KB） |
| 页帧 Frame | frame | 内存里装「页」的格子 |
| 缓冲区 buffer pool | buffer pool | 内存里放页的池子；内存小，池子有限 |
| 淘汰 eviction | eviction | 池子满了，赶走一个页，给新页腾地方 |
| **LRU** | Least Recently Used | 淘汰「最久没被碰过」的那个页（像手机后台杀最久没用的 App） |
| pin 钉住 | pin / pin count | 正在用的页不能赶走；用完要 unpin 释放 |
| 脏页 dirty page | dirty page | 被改过、和硬盘不一致的页；淘汰前先写回硬盘（flush 刷盘） |
| SQL 解析 parser | parser | 把「select ...」这句话拆成程序能懂的语法树 |
| 执行器 executor | executor | 按语法树真正去读表、算结果 |
| 索引 index | index | 书的目录，加速查找；数据库里常用 B+ 树 |
| 事务 transaction | transaction | 一组要么全成功、要么全失败的数据库操作 |
| MVCC | Multi-Version Concurrency Control | 多版本并发控制：读不挡写、写不挡读 |
| LSM-Tree | Log-Structured Merge Tree | 写多读少的存储结构（先写内存表，再合并到磁盘） |
| 向量 vector | vector | 一串数字，表示一段内容的「语义坐标」 |
| Embedding 嵌入 | embedding | 把文字/图片变成向量的过程 |
| ANN | Approximate Nearest Neighbor | 在向量库里「找最像的几个」，近似算法更快 |
| IVF-Flat | Inverted File Flat | 一种 ANN 索引：先聚类分桶，再在桶里精确找 |
| RAG | Retrieval-Augmented Generation | 先检索资料、再让大模型照着答，减少胡编 |
| Chunk 分块 | chunk | 把长文档切成小段，方便检索 |
| Token | token | 大模型计量的「字块」；API 按 token 收费 |
| Agent 智能体 | agent | 让 AI 自己调用工具、分步骤完成任务的程序 |
| 提测 | submission | 把代码交到官方平台跑评测、拿分数 |
| 训练营 | training camp | 官方评测平台，可提交代码看测试结果 |
