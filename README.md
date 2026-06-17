> **🤖 AI-Maintained** — This repository is maintained by AI agents. Human commits (perhaps) zero. Liability (certainly) none. Fun (definitely) infinite.

# IT4IT Skill - IT 管理参考架构

## 概述

IT4IT 是 The Open Group 发布的 IT 管理参考架构，为管理 IT 业务提供了规范性的框架。它定义了 IT 价值链、价值流、功能组件和数据对象，帮助 IT 组织实现端到端的 IT 服务管理。

## 何时使用

当用户需要：
- 了解或应用 IT4IT 参考架构
- 设计 IT 服务管理体系
- 优化 IT 价值链和价值流
- 选择和集成 IT 管理工具
- 建立 IT 运营模型
- 实施 DevOps 和敏捷 IT

## IT4IT 核心概念

### IT 价值链

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                           IT4IT Value Chain                                  │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌─────────────┐   ┌─────────────┐   ┌─────────────┐   ┌─────────────┐     │
│  │  Strategy   │   │   Design    │   │   Source    │   │   Consume   │     │
│  │  to         │──►│   to        │──►│   to        │──►│   to        │     │
│  │  Portfolio  │   │   Fulfill   │   │   Deploy    │   │   Retire    │     │
│  │  (S2P)      │   │   (D2F)     │   │   (S2D)     │   │   (C2R)     │     │
│  └─────────────┘   └─────────────┘   └─────────────┘   └─────────────┘     │
│        │                 │                 │                 │              │
│        ▼                 ▼                 ▼                 ▼              │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │              Supporting Activities & Governance                      │   │
│  │  • Intelligence & Reporting  • Governance, Risk & Compliance        │   │
│  │  • Sourcing & Vendor Mgmt    • Finance & Assets                     │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 四大价值流

| 价值流 | 英文名称 | 核心目标 | 关键产出 |
|--------|---------|---------|---------|
| **S2P** | Strategy to Portfolio | 将业务战略转化为 IT 投资组合 | IT Portfolio |
| **D2F** | Design to Fulfill | 设计并交付 IT 服务 | Service Release |
| **S2D** | Source to Deploy | 采购和部署 IT 资源 | Deployed Components |
| **C2R** | Consume to Retire | 管理服务消费到退役 | Service Experience |

## 价值流详解

### Value Stream 1: Strategy to Portfolio (S2P)

**目标**: 将业务需求转化为经过优先级排序的 IT 投资组合

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    Strategy to Portfolio (S2P)                               │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  输入: Business Strategy, Business Demand                                    │
│                                                                              │
│  ┌───────────────┐    ┌───────────────┐    ┌───────────────┐               │
│  │   Strategy    │    │   Portfolio   │    │   Proposal    │               │
│  │   Management  │───►│   Demand      │───►│   Management  │               │
│  │               │    │   Management  │    │               │               │
│  └───────────────┘    └───────────────┘    └───────────────┘               │
│         │                    │                    │                         │
│         ▼                    ▼                    ▼                         │
│  ┌───────────────┐    ┌───────────────┐    ┌───────────────┐               │
│  │   Policy      │    │   Portfolio   │    │   Portfolio   │               │
│  │   Management  │    │   Planning    │    │   Approval    │               │
│  │               │    │               │    │               │               │
│  └───────────────┘    └───────────────┘    └───────────────┘               │
│                                                                              │
│  输出: Approved IT Portfolio, Conceptual Service                            │
│                                                                              │
│  关键数据对象:                                                               │
│  • Conceptual Service                                                        │
│  • Initiative                                                                │
│  • Service Portfolio                                                         │
│  • IT Investment                                                             │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

**功能组件**:

| 功能组件 | 描述 |
|---------|------|
| Strategy Management | 管理 IT 战略与业务战略的对齐 |
| Portfolio Demand Management | 收集和管理业务需求 |
| Proposal Management | 管理 IT 提案和业务案例 |
| Policy Management | 定义和管理 IT 策略 |
| Portfolio Planning | 规划 IT 投资组合 |
| Portfolio Approval | 审批投资组合项目 |

---

### Value Stream 2: Design to Fulfill (D2F)

**目标**: 设计、开发和交付 IT 服务

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                      Design to Fulfill (D2F)                                 │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  输入: Conceptual Service, Requirements                                      │
│                                                                              │
│  ┌───────────────┐    ┌───────────────┐    ┌───────────────┐               │
│  │   Service     │    │   Service     │    │   Service     │               │
│  │   Design      │───►│   Development │───►│   Release     │               │
│  │               │    │               │    │               │               │
│  └───────────────┘    └───────────────┘    └───────────────┘               │
│         │                    │                    │                         │
│         ▼                    ▼                    ▼                         │
│  ┌───────────────┐    ┌───────────────┐    ┌───────────────┐               │
│  │   Functional  │    │   Defect      │    │   Service     │               │
│  │   Requirement │    │   Management  │    │   Catalog     │               │
│  │   Management  │    │               │    │   Management  │               │
│  └───────────────┘    └───────────────┘    └───────────────┘               │
│                                                                              │
│  输出: Logical Service, Service Release, Service Catalog                    │
│                                                                              │
│  关键数据对象:                                                               │
│  • Logical Service                                                           │
│  • Service Release                                                           │
│  • Requirement                                                               │
│  • Defect                                                                    │
│  • Service Blueprint                                                         │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

**功能组件**:

| 功能组件 | 描述 |
|---------|------|
| Service Design | 设计服务架构和蓝图 |
| Service Development | 开发和构建服务 |
| Service Release | 管理服务发布 |
| Functional Requirement Management | 管理功能需求 |
| Defect Management | 管理缺陷和问题 |
| Service Catalog Management | 管理服务目录 |

---

### Value Stream 3: Source to Deploy (S2D)

**目标**: 采购、构建和部署 IT 资源

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                       Source to Deploy (S2D)                                 │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  输入: Service Release, Deployment Requirements                              │
│                                                                              │
│  ┌───────────────┐    ┌───────────────┐    ┌───────────────┐               │
│  │   Source      │    │   Build       │    │   Deploy      │               │
│  │   Selection   │───►│   Package     │───►│   Release     │               │
│  │               │    │               │    │               │               │
│  └───────────────┘    └───────────────┘    └───────────────┘               │
│         │                    │                    │                         │
│         ▼                    ▼                    ▼                         │
│  ┌───────────────┐    ┌───────────────┐    ┌───────────────┐               │
│  │   Offer       │    │   Offer       │    │   Change      │               │
│  │   Management  │    │   Consumption │    │   Control     │               │
│  │               │    │               │    │               │               │
│  └───────────────┘    └───────────────┘    └───────────────┘               │
│                                                                              │
│  输出: Deployed Service, Actual Service, Configuration Items                │
│                                                                              │
│  关键数据对象:                                                               │
│  • Actual Service                                                            │
│  • Source Blueprint                                                          │
│  • Release Package                                                           │
│  • Configuration Item (CI)                                                   │
│  • Change Record                                                             │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

**功能组件**:

| 功能组件 | 描述 |
|---------|------|
| Source Selection | 选择供应商和资源来源 |
| Build Package | 构建部署包 |
| Deploy Release | 部署发布包到环境 |
| Offer Management | 管理供应商产品 |
| Offer Consumption | 管理资源消费 |
| Change Control | 控制变更流程 |

---

### Value Stream 4: Consume to Retire (C2R)

**目标**: 管理服务的消费、支持和退役

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                       Consume to Retire (C2R)                                │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  输入: Actual Service, Service Request                                       │
│                                                                              │
│  ┌───────────────┐    ┌───────────────┐    ┌───────────────┐               │
│  │   Request     │    │   Service     │    │   Service     │               │
│  │   Management  │───►│   Level       │───►│   Monitoring  │               │
│  │               │    │   Management  │    │               │               │
│  └───────────────┘    └───────────────┘    └───────────────┘               │
│         │                    │                    │                         │
│         ▼                    ▼                    ▼                         │
│  ┌───────────────┐    ┌───────────────┐    ┌───────────────┐               │
│  │   Incident    │    │   Problem     │    │   Usage &     │               │
│  │   Management  │    │   Management  │    │   Consumption │               │
│  │               │    │               │    │   Analytics   │               │
│  └───────────────┘    └───────────────┘    └───────────────┘               │
│                                                                              │
│  输出: Service Experience, Usage Data, Retirement Candidate                 │
│                                                                              │
│  关键数据对象:                                                               │
│  • Service Contract                                                          │
│  • Incident Record                                                           │
│  • Problem Record                                                            │
│  • Service Level Agreement (SLA)                                             │
│  • Usage Record                                                              │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

**功能组件**:

| 功能组件 | 描述 |
|---------|------|
| Request Management | 管理服务请求 |
| Service Level Management | 管理服务级别 |
| Service Monitoring | 监控服务状态 |
| Incident Management | 管理事件 |
| Problem Management | 管理问题 |
| Usage & Consumption Analytics | 分析使用和消费数据 |

---

## IT4IT 数据对象模型

### 核心数据对象

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                      IT4IT Data Object Model                                 │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  Service Backbone (服务主干):                                                │
│                                                                              │
│  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐    ┌──────────┐  │
│  │ Conceptual   │───►│  Logical     │───►│  Actual      │───►│ Service  │  │
│  │ Service      │    │  Service     │    │  Service     │    │ Contract │  │
│  │ (S2P)        │    │  (D2F)       │    │  (S2D)       │    │ (C2R)    │  │
│  └──────────────┘    └──────────────┘    └──────────────┘    └──────────┘  │
│                                                                              │
│  Supporting Objects:                                                         │
│                                                                              │
│  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐                   │
│  │ Initiative   │    │ Requirement  │    │ Release      │                   │
│  │              │    │              │    │ Package      │                   │
│  └──────────────┘    └──────────────┘    └──────────────┘                   │
│                                                                              │
│  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐                   │
│  │ Change       │    │ Incident     │    │ Problem      │                   │
│  │ Record       │    │ Record       │    │ Record       │                   │
│  └──────────────┘    └──────────────┘    └──────────────┘                   │
│                                                                              │
│  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐                   │
│  │ Configuration│    │ Knowledge    │    │ Usage        │                   │
│  │ Item (CI)    │    │ Article      │    │ Record       │                   │
│  └──────────────┘    └──────────────┘    └──────────────┘                   │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 服务主干 (Service Backbone)

服务主干是 IT4IT 的核心概念，贯穿四个价值流：

| 数据对象 | 所属价值流 | 描述 |
|---------|-----------|------|
| **Conceptual Service** | S2P | 服务的概念定义，包含业务价值 |
| **Logical Service** | D2F | 服务的逻辑设计，包含架构蓝图 |
| **Actual Service** | S2D | 服务的实际部署实例 |
| **Service Contract** | C2R | 服务的消费合同，包含 SLA |

---

## 与其他框架的关系

### IT4IT vs ITIL

| 维度 | IT4IT | ITIL |
|------|-------|------|
| **定位** | 参考架构 | 最佳实践 |
| **范围** | 端到端 IT 价值链 | IT 服务管理流程 |
| **视角** | 工具和自动化驱动 | 流程和人员驱动 |
| **数据** | 明确的数据对象模型 | 流程数据隐含 |
| **关系** | 互补 | 互补 |

### IT4IT 与 ITIL 流程映射

| IT4IT 功能组件 | ITIL 流程 |
|---------------|----------|
| Service Design | Service Design |
| Service Release | Release Management |
| Change Control | Change Management |
| Incident Management | Incident Management |
| Problem Management | Problem Management |
| Service Level Management | Service Level Management |
| Service Catalog Management | Service Catalog Management |

### IT4IT vs TOGAF

| 维度 | IT4IT | TOGAF |
|------|-------|-------|
| **定位** | IT 运营参考架构 | 企业架构框架 |
| **范围** | IT 服务管理 | 全企业架构 |
| **视角** | IT 内部运营 | 业务-IT 对齐 |
| **互补** | 可作为 TOGAF 技术架构的一部分 | 提供更广泛的架构方法 |

---

## 实施指南

### 实施路径

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    IT4IT Implementation Roadmap                              │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  Phase 1: Foundation (基础)                                                  │
│  ├── 评估当前 IT 管理成熟度                                                   │
│  ├── 识别价值流差距                                                          │
│  ├── 定义目标运营模型                                                         │
│  └── 建立治理框架                                                            │
│                                                                              │
│  Phase 2: Core Value Streams (核心价值流)                                    │
│  ├── 实施 S2D (Source to Deploy)                                            │
│  │   └── CI/CD 管道、配置管理、变更控制                                       │
│  ├── 实施 C2R (Consume to Retire)                                           │
│  │   └── 服务台、事件管理、问题管理                                           │
│  └── 集成和自动化                                                            │
│                                                                              │
│  Phase 3: Extended Value Streams (扩展价值流)                                │
│  ├── 实施 D2F (Design to Fulfill)                                           │
│  │   └── 服务设计、开发、发布管理                                             │
│  ├── 实施 S2P (Strategy to Portfolio)                                       │
│  │   └── 需求管理、组合规划、投资管理                                         │
│  └── 端到端集成                                                              │
│                                                                              │
│  Phase 4: Optimization (优化)                                                │
│  ├── 数据驱动的决策                                                          │
│  ├── 持续改进                                                                │
│  └── AI/ML 增强                                                              │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 工具映射

将 IT4IT 功能组件映射到常见工具：

| 功能组件 | 开源工具 | 商业工具 |
|---------|---------|---------|
| Service Design | Archi, Draw.io | ServiceNow, Sparx EA |
| Service Development | GitLab, Jenkins | Azure DevOps, Jira |
| Service Release | ArgoCD, Flux | ServiceNow, BMC |
| Build Package | Docker, Kubernetes | AWS, Azure |
| Deploy Release | Ansible, Terraform | Puppet, Chef |
| Change Control | GitLab, ServiceNow | ServiceNow, BMC |
| Incident Management | Zammad, osTicket | ServiceNow, Jira SM |
| Problem Management | - | ServiceNow, BMC |
| Service Monitoring | Prometheus, Grafana | Datadog, Splunk |
| CMDB | i-doit, CMDBuild | ServiceNow, BMC |

---

## 最佳实践

### 1. 以服务为中心

```
建议:
- 建立统一的服务定义标准
- 使用服务主干贯穿各价值流
- 确保服务数据的一致性和完整性
```

### 2. 自动化优先

```
建议:
- 优先自动化重复性任务
- 建立自动化工具链
- 实现端到端的自动化流水线
- 关注 AIOps 和智能自动化
```

### 3. 数据驱动

```
建议:
- 定义清晰的数据对象模型
- 确保数据质量和完整性
- 建立数据治理机制
- 利用数据进行决策和优化
```

### 4. 渐进式实施

```
建议:
- 从核心价值流开始（S2D, C2R）
- 逐步扩展到完整价值链
- 持续评估和调整
- 关注快速价值交付
```

### 5. 工具整合

```
建议:
- 避免工具孤岛
- 建立工具集成架构
- 使用 API 和事件驱动集成
- 考虑平台化方案
```

---

## 资源文件

### 模板文件
- `assets/it4it-value-chain.drawio` - IT4IT 价值链图

### 参考文档
- `references/value-stream-guide.md` - 价值流详解
- `references/data-object-model.md` - 数据对象模型
- `references/tool-mapping-guide.md` - 工具映射指南

### 脚本工具
- `scripts/validate-it4it.js` - IT4IT 合规验证脚本

---

## 常见问题

### Q1: IT4IT 和 ITIL 应该如何结合使用？

A: IT4IT 提供参考架构和数据模型，ITIL 提供流程最佳实践：
- 使用 IT4IT 定义工具架构和数据流
- 使用 ITIL 定义流程和角色
- 两者互补而非替代

### Q2: 如何确定实施的优先级？

A: 建议优先级：
1. **S2D + C2R**: 核心运营能力，直接影响服务交付
2. **D2F**: 支持敏捷和 DevOps
3. **S2P**: 战略对齐和投资管理

### Q3: 小型 IT 组织是否需要完整实施 IT4IT？

A: 不需要：
- 根据组织规模选择关键功能组件
- 从核心价值流开始
- 渐进式扩展

### Q4: 如何衡量 IT4IT 实施效果？

A: 关键指标：
- 服务交付周期时间
- 变更成功率
- 事件解决时间
- 服务可用性
- IT 成本效率

---

## 更新日志

- **v1.0.0** (2025-01-24): 初始版本
  - IT4IT 价值链和四大价值流
  - 功能组件详解
  - 数据对象模型
  - 实施指南和最佳实践
