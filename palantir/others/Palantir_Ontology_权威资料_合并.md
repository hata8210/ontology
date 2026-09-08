# Palantir Ontology 架构参考(官方文档合并版)

> 来源:Palantir Foundry 官方文档(一手权威),抓取于 2026-09-05
> 说明:以下内容由官方文档各 overview 页面合并整理,保留原文关键表述并附中文说明;如需最新细节请以官方文档为准(每节附原文链接)。

---

## 1. Ontology 总览(Ontology Building)

**原文链接:** https://www.palantir.com/docs/foundry/ontology/overview

- **定位**:Palantir Ontology 是组织的**运营层(operational layer)**。
- **位置**:位于已集成数字资产(数据集 datasets、虚拟表 virtual tables、模型 models)之上,把这些资产连接到**现实世界对应物**(physical assets:工厂 plant、设备 equipment、产品 product;概念:客户订单、金融交易)。
- **本质**:在很多场景下,Ontology 就是组织的**数字孪生(digital twin)**,包含两类元素:
  - **语义元素(semantic elements)**:对象 objects、属性 properties、链接 links
  - **动态元素(kinetic elements)**:动作 actions、函数 functions、动态安全 dynamic security

> 关键句(原文):"Rather than being an abstract data model, the Foundry Ontology maps each ontological concept to an organization's actual data"——**它不是抽象数据模型,而是把本体概念映射到组织的真实数据上**。

---

## 2. 对象类型(Object Types)

**原文链接:** https://www.palantir.com/docs/foundry/object-link-types/object-types-overview/

三层概念:
| 概念 | 定义 | 类比数据集 |
|---|---|---|
| **Object type(对象类型)** | 现实实体/事件的 **schema 定义** | dataset(表结构) |
| **Object(对象/实例)** | 某个对象类型的**单个实例** | 表里的一行(row) |
| **Object set(对象集合)** | 多个对象实例的**集合** | 筛选后的行集合(filtered rows) |

**示例**:`Employee` 对象类型定义"所有员工"的特征;单个员工 "Melissa Chang" 是 object;"All tenured employees"(所有资深员工)是 object set。`Flight` 同理:"JFK → SFO 2021-02-24" 是单实例。

**关键点**:对象通过**挂接数据源(backing datasources)** 创建并显示在应用中——把企业数据源(如员工目录)接入对象类型,对象才有真实数据支撑。

---

## 3. 链接类型(Link Types)

**原文链接:** https://www.palantir.com/docs/foundry/object-link-types/link-types-overview/

- **Link type(链接类型)** = 两个对象类型之间关系的 **schema 定义**;**link** = 该关系的一个实例。
- 示例:Employee ↔ Company 定义 "Employee–Employer";Flight ↔ Aircraft 定义 "Scheduled Flight–Assigned Aircraft"。
- **同类型对象也可链接**:如 Employee 与自身定义 `Direct Report ↔ Manager`。
- **不支持跨 Ontology 链接**;跨库场景建议用共享 Ontology(shared Ontology)。

**方向性(Directionality)**:
- 链接类型**天生双向**:一条 link type 永远有两侧,每侧可独立遍历,各有自己的显示名和 API 名。
- 例:`flight.assignedAircraft.get()` 走 Aircraft 侧;`aircraft.flights.all()` 走 Flight 侧。
- **不需要**为同一关系反向再建一条 link type——单条双向即可,两侧独立。

---

## 4. 动作类型与函数(Action Types & Functions)

**原文链接:**
- Actions: https://www.palantir.com/docs/foundry/action-types/overview/
- Functions: https://www.palantir.com/docs/foundry/functions/overview/

- **Action(动作)**:一个**事务性变更**,基于用户定义的逻辑修改一个或多个对象的属性。
- **Action type(动作类型)**:一次可执行的一组变更(对象/属性值/链接)的**定义**,包含提交时的**副作用行为(side effects)**。
- **示例** `Assign Employee`:HR 员工把 "Melissa Chang" 的角色改为 "Product Manager",该动作可:
  - 要求参数输入(标准化表单)
  - 自动创建 Employee 与 Manager 之间的链接
  - 副作用:通知新旧经理
  - 校验:仅授权 HR 可执行
- **治理意义**:用户决策和洞察以"对 Ontology 的编辑"形式沉淀,数据资产越用越有价值;动作逻辑与校验在所有应用中保持一致。
- 变更提交后会写回(writeback),并在全部用户应用即时生效。
- **Functions**:用于编写/演进任意复杂度的业务逻辑(官网另有专页,未在此抓取细节)。

---

## 5. 接口(Interfaces)

**原文链接:** https://www.palantir.com/docs/foundry/interfaces/interface-overview/

- **Interface** = 描述对象类型**形状(shape)与能力(capabilities)** 的 Ontology 类型,提供**对象类型多态**。
- **示例**:`Facility` 接口含 Facility Name、Location 属性;`Airport`、`Manufacturing Plant`、`Maintenance Hangar` 都可实现它,并各自附加专属属性。
- **价值**:工作流无需感知具体对象类型即可聚合/独立操作多类对象;未来新增实现该接口的对象类型,工作流**零改造**即可兼容。
- **组成**:接口属性(interface properties,可本地定义或用共享属性)、链接类型约束、动作类型约束、元数据。
- **继承**:类似编程语言接口,可**扩展接口**(子接口继承父接口属性再加专属属性);对象类型可实现**多个接口**用于不同工作流。

---

## 6. 概念对照(理解要点)

| Palantir Ontology | 学术/通用概念 |
|---|---|
| Object type | 类(class)/实体类型 |
| Object / Object set | 实例 / 实例集合 |
| Link type | 关系(relation/object property) |
| Action type | 业务操作/写操作(带约束与副作用) |
| Interface | 抽象类型/多态(interface) |
| Properties | 数据属性(data property) |

**注意**:Palantir Ontology 是**面向运营与治理的工程化语义层**,强调与真实数据绑定、细粒度安全、动作驱动的变更;不同于以逻辑推理为核心的学术 OWL 本体。二者"语义建模"思想相通,但目标与实现路径不同。

---

## 附:相关论文

- **《Concept-centric Software Development》(arXiv:2304.14975)** — 讨论 Palantir 将软件开发重构为"概念为中心";已下载 PDF 并上传至 RAGFlow 知识库。
- 官方实操课程(创建第一个 Ontology): https://learn.palantir.com/deep-dive-creating-your-first-ontology
