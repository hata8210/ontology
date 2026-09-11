# Ontology

Palantir Foundry **Ontology**（本体）体系与 LLM 生成本体研究的资料集。

本项目围绕 Palantir 架构的核心——**Ontology 本体体系**——整理了一批一手权威资料，并逐步扩展为覆盖「权威资料 → 基础背景 → 工程实践 → 相关项目」的完整知识库：

- **Palantir 侧**：基于官方文档整理的交付核心与落地架构参考（含中文注释），以及官方入门教程 PDF。
- **LLM 侧**：关于使用大语言模型（LLM）生成/推理本体论的学术论文（英文原文 PDF）。
- **工程侧**：DDD 领域驱动设计、事件风暴等落地本体/业务建模所需的方法论。
- **行业侧**：本体论结合大模型/智能体落地的会议纪要、竞品/产品调研。
- **项目侧**：与本体相关的开源项目与自研 Skill（仅维护指向各自文档的入口）。

> 核心观点：Ontology 不是抽象的静态数据模型，而是将企业的“名词”（对象/属性/链接）与“动词”（动作/函数/逻辑）统一映射到真实数据与业务流程上，从而支撑**人机协同的运营决策**。

## 目录结构

```text
.
├── palantir/                     # Palantir Ontology 交付/架构参考 + 官方入门教程
│   ├── Palantir官方教程/                   # Palantir Learn 官方教程 PDF（入门首选）
│   ├── others/                              # 官方文档整理版（含中文注释）
│   └── 分享讲解/                           # Palantir 主题分享/讲解（视频转写 + 讲解明细）
├── paper/                        # LLM 生成本体论相关论文（英文 PDF）
├── context/                      # 本体论基础背景资料（概念、RDFS/OWL、视频讲解）
├── ddd/                          # DDD 架构方法论（战略/战术设计、事件风暴、SOLID）
├── others/                       # 行业交流纪要 / 竞品产品调研
├── semantica/                    # 相关项目：开源图原生知识图谱基础设施
│   ├── semantica-main/                     # Semantica 源码仓库
│   ├── docs/                             # 官方文档（Markdown）
│   └── website/                          # 官网资料整理（PDF）
└── projects/                     # 相关项目（本体 Skill）
```

## 内容概览

### Palantir Ontology 体系

| 路径 | 主题 |
| --- | --- |
| `Palantir官方教程/` | Palantir Learn 官方教程：Getting Started、Foundry & AIP 介绍、Application Development（构建首个应用 / 创建首个 Ontology）、Data Engineering（构建首个 Pipeline / E2E 工作流）。 |
| `others/` | 官方文档整理版（含中文注释）：标准三平台架构（AIP + Foundry + Apollo）、Ontology System 交付核心、Ontology 核心概念（对象/属性/链接/动作/函数）。 |
| `分享讲解/` | Palantir 主题分享与讲解（转写文本 + 讲解明细）：LLM 驱动 Ontology 构建、Palantir Agent 与 Ontology 交互、企业 Agentic Workflow 落地、文件如何变成 Ontology、本体设计原则与实践。 |

### LLM 与本体生成

| 文件 | 主题 |
| --- | --- |
| `Concept-centric_Software_Development_2304.14975.pdf` | 以概念为中心的软件开发。 |
| `LLMs_Generate_Capability_Ontologies.pdf` | 用 LLM 生成能力本体。 |
| `NeurOWL_LLM_Neural-symbolic_OWL_Reasoning.pdf` | 神经-符号 OWL 推理。 |
| `Ontology_Generation_using_LLMs.pdf` | 使用 LLM 进行本体生成。 |

### 基础背景（context）

| 文件 | 主题 |
| --- | --- |
| `ontology是什么东西 - Google Search.pdf` | 本体论基础概念科普（搜索结果整理）。 |
| `rdfs和owl分别是什么有什么关联 - Google Search.pdf` | RDFS 与 OWL 的差异与关联。 |
| `owl与ontology相关概念SHACL、SKOS、Compliance Rules、W3C、PROV-O、SPARQL、HermiT.md` | 语义网与 AI 治理技术栈大白话讲解，及其与 OWL/Ontology 的关系。 |
| `视频：为什么智能体系统需要本体论 20260907.txt` | Frank Coyle（UC Berkeley）演讲全文转写：智能体与本体、知识表示。 |
| `视频：本体论Ontology的新瓶与旧酒 20260903.txt` | 腾讯云架构师同盟播客「架构达尔文」对谈转写：本体论在 AI/架构师语境下的演进。 |

### 工程方法论（ddd）

| 文件 | 主题 |
| --- | --- |
| `DDD架构指导思想.md` | DDD 战略设计（统一语言、子域、界限上下文）与战术设计要点。 |
| `Event Storm敏捷架构指导思想.md` | 事件风暴工作坊实践：用彩色便签快速梳理业务全景、划定界限上下文。 |
| `SOLID编程指导思想.md` | 面向对象设计的五大原则（SRP、OCP、LSP、ISP、DIP）。 |
| `Domain Driven Design ... - Eric Evans.pdf` | Eric Evans《领域驱动设计》英文原版 PDF。 |

### 行业交流与产品参考（others）

| 文件 | 主题 |
| --- | --- |
| `其它产品一 20260908.txt` | 会议纪要：本体论 + 大模型 + 智能体落地实践（逆向工程构建本体、子域本体+桥接、本体作为智能体“蓝图”）。 |

## 相关项目

> 本目录为相关项目代码，主要维护指向各项目文档的入口，不展开代码细节。

| 项目 | 说明 | 入口 |
| --- | --- | --- |
| `ontology-1/` | 面向智能体记忆的**类型化知识图谱** Skill：实体（Person / Project / Task / Event / Document 等）+ 类型约束 + 关系链接，支持增删改查、约束校验与跨 Skill 状态共享。 | 详见 `projects/ontology-1/SKILL.md` |
| `semantica/semantica-main/` | 开源**图原生基础设施**（semantica-agi/semantica）：面向高合规领域（金融、医疗、政务等）的上下文与可问责 AI 系统，提供 Context Graph / 知识图谱构建、本体治理（OWL、SHACL、SKOS）、确定性推理与全链路溯源。 | 详见 `semantica/semantica-main/README.md` |
| `semantica/docs/` | Semantica 官方文档（markdown）：架构、模块、安装、参考手册、指南与集成说明。 | 详见 `semantica/docs/` |
| `semantica/website/` | Semantica 官网资料整理（PDF）：Architecture、Core Concepts（Glossary / Modules / Choose the Right Module）、Overview（Reasoning & Rules / SHACL Validation / Decision Intelligence / Ontology Management）。 | 详见 `semantica/website/` |

## 说明

- **来源**：Palantir 官方文档为**一手权威**来源，抓取于 2026-09 上旬；学术论文为公开发表的英文论文；视频与会议资料为 AI 语音识别/整理稿，可能存在误差。
- **语言**：Palantir 侧文档以中文为主（保留原文关键表述）；论文 PDF 为英文原文。
- **用途**：作为 Ontology 体系研究、交付落地、工程实践与 LLM 生成本体方向的参考资料。
