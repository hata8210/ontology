# Ontology

Palantir Foundry **Ontology**（本体）体系与 LLM 生成本体研究的资料集。

本项目围绕 Palantir 架构的核心——**Ontology 本体体系**——整理了一批一手权威资料：

- **Palantir 侧**：基于官方文档整理的交付核心与落地架构参考（含中文注释）。
- **LLM 侧**：关于使用大语言模型（LLM）生成/推理本体论的学术论文（英文原文 PDF）。

> 核心观点：Ontology 不是抽象的静态数据模型，而是将企业的“名词”（对象/属性/链接）与“动词”（动作/函数/逻辑）统一映射到真实数据与业务流程上，从而支撑**人机协同的运营决策**。

## 目录结构

```text
.
├── palantir/                     # Palantir Ontology 交付/架构参考（官方文档整理，附中文说明）
│   ├── 01_platforms_apollo_delivery.md     # 标准三平台架构 AIP + Foundry + Apollo
│   ├── 02_ontology_system.md               # Ontology System（交付核心）
│   └── Palantir_Ontology_权威资料_合并.md   # Ontology 架构参考（官方文档合并版）
└── paper/                        # LLM 生成本体论相关论文（英文 PDF）
    ├── Concept-centric_Software_Development_2304.14975.pdf
    ├── LLMs_Generate_Capability_Ontologies.pdf
    ├── NeurOWL_LLM_Neural-symbolic_OWL_Reasoning.pdf
    └── Ontology_Generation_using_LLMs.pdf
```

## 内容概览

### Palantir Ontology 体系

| 文件 | 主题 |
| --- | --- |
| `01_platforms_apollo_delivery.md` | Palantir 标准三平台架构（AIP + Foundry + Apollo），以及作为企业操作系统的定位。 |
| `02_ontology_system.md` | Ontology 系统的四重集成：**数据**（data）、**逻辑**（logic）、**动作**（action）、**安全**（security）。 |
| `Palantir_Ontology_权威资料_合并.md` | 官方文档 Overview 合并整理版：对象、属性、链接、动作、函数等核心概念。 |

### LLM 与本体生成

| 文件 | 主题 |
| --- | --- |
| `Concept-centric_Software_Development_2304.14975.pdf` | 以概念为中心的软件开发。 |
| `LLMs_Generate_Capability_Ontologies.pdf` | 用 LLM 生成能力本体。 |
| `NeurOWL_LLM_Neural-symbolic_OWL_Reasoning.pdf` | 神经-符号 OWL 推理。 |
| `Ontology_Generation_using_LLMs.pdf` | 使用 LLM 进行本体生成。 |

## 说明

- **来源**：Palantir 官方文档为**一手权威**来源，抓取于 2026-09 上旬；学术论文为公开发表的英文论文。
- **语言**：Palantir 侧文档以中文为主（保留原文关键表述）；论文 PDF 为英文原文。
- **用途**：作为 Ontology 体系研究、交付落地与 LLM 生成本体方向的参考资料。

## License

本仓库为个人学习与研究资料整理，版权归原作者所有，仅供个人参考使用。
