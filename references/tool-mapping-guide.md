# IT4IT 工具映射指南

本指南将 IT4IT 功能组件映射到常见的 IT 管理工具。

## 工具映射总览

### 按价值流分类

| 价值流 | 功能组件 | 开源工具 | 商业工具 |
|-------|---------|---------|---------|
| **S2P** | Strategy Management | - | ServiceNow SPM, Planview |
| S2P | Portfolio Demand | Taiga, OpenProject | Jira Portfolio, Azure Boards |
| S2P | Proposal Management | - | ServiceNow, Planview |
| S2P | Policy Management | OPA | ServiceNow GRC |
| S2P | Portfolio Planning | OpenProject | Planview, Clarity |
| **D2F** | Service Design | Archi, Draw.io | Sparx EA, ServiceNow |
| D2F | Service Development | GitLab, Jenkins | Azure DevOps, Jira |
| D2F | Service Release | ArgoCD, Flux | ServiceNow, BMC |
| D2F | Requirement Management | Taiga | Jira, Azure DevOps |
| D2F | Defect Management | Mantis, Bugzilla | Jira, Azure DevOps |
| D2F | Service Catalog | - | ServiceNow, BMC |
| **S2D** | Source Selection | - | SAP Ariba, Coupa |
| S2D | Build Package | Docker, Buildah | - |
| S2D | Deploy Release | Ansible, Terraform | Puppet, Chef |
| S2D | Offer Management | - | ServiceNow, BMC |
| S2D | Change Control | GitLab MR | ServiceNow, BMC |
| **C2R** | Request Management | Zammad, osTicket | ServiceNow, Jira SM |
| C2R | Service Level Mgmt | - | ServiceNow, BMC |
| C2R | Service Monitoring | Prometheus, Grafana | Datadog, Splunk |
| C2R | Incident Management | Zammad | ServiceNow, PagerDuty |
| C2R | Problem Management | - | ServiceNow, BMC |
| C2R | Usage Analytics | ELK Stack | Splunk, Datadog |

---

## 详细工具对比

### 开发和交付工具 (D2F + S2D)

#### 版本控制

| 工具 | 类型 | IT4IT 组件 | 特点 |
|------|------|-----------|------|
| GitLab | 开源/商业 | Service Development | 完整 DevOps 平台 |
| GitHub | 商业 | Service Development | Actions, Copilot |
| Bitbucket | 商业 | Service Development | Atlassian 生态 |

#### CI/CD

| 工具 | 类型 | IT4IT 组件 | 特点 |
|------|------|-----------|------|
| GitLab CI | 开源/商业 | Build Package | 原生集成 |
| Jenkins | 开源 | Build Package | 插件生态丰富 |
| GitHub Actions | 商业 | Build Package | YAML 配置 |
| Azure Pipelines | 商业 | Build Package | 云原生 |

#### 容器和编排

| 工具 | 类型 | IT4IT 组件 | 特点 |
|------|------|-----------|------|
| Docker | 开源 | Build Package | 容器标准 |
| Kubernetes | 开源 | Deploy Release | 容器编排 |
| OpenShift | 商业 | Deploy Release | 企业级 K8s |

#### GitOps

| 工具 | 类型 | IT4IT 组件 | 特点 |
|------|------|-----------|------|
| ArgoCD | 开源 | Deploy Release | 声明式部署 |
| Flux | 开源 | Deploy Release | GitOps 工具包 |
| Spinnaker | 开源 | Deploy Release | 多云部署 |

#### 基础设施即代码

| 工具 | 类型 | IT4IT 组件 | 特点 |
|------|------|-----------|------|
| Terraform | 开源 | Deploy Release | 多云 IaC |
| Ansible | 开源 | Deploy Release | 配置管理 |
| Pulumi | 开源/商业 | Deploy Release | 编程语言 IaC |

---

### ITSM 工具 (C2R)

#### 综合 ITSM 平台

| 工具 | 类型 | 覆盖组件 | 特点 |
|------|------|---------|------|
| ServiceNow | 商业 | 全部 C2R | 市场领导者 |
| BMC Helix | 商业 | 全部 C2R | 企业级 |
| Jira Service Management | 商业 | Request, Incident | Atlassian 生态 |
| Freshservice | 商业 | Request, Incident | 中小企业 |

#### 开源 ITSM

| 工具 | 类型 | 覆盖组件 | 特点 |
|------|------|---------|------|
| Zammad | 开源 | Request, Incident | 现代化界面 |
| osTicket | 开源 | Request | 简单工单 |
| GLPI | 开源 | Request, Asset | 资产管理 |

---

### 监控和可观测性 (C2R)

#### 指标监控

| 工具 | 类型 | 特点 |
|------|------|------|
| Prometheus | 开源 | 时序数据库，云原生标准 |
| InfluxDB | 开源 | 时序数据库 |
| Datadog | 商业 | SaaS 全栈监控 |
| New Relic | 商业 | APM 领导者 |

#### 可视化

| 工具 | 类型 | 特点 |
|------|------|------|
| Grafana | 开源 | 多数据源仪表盘 |
| Kibana | 开源 | ELK 栈可视化 |

#### 日志管理

| 工具 | 类型 | 特点 |
|------|------|------|
| Loki | 开源 | 轻量级日志聚合 |
| Elasticsearch | 开源 | 全文搜索引擎 |
| Splunk | 商业 | 企业级日志分析 |

#### 告警

| 工具 | 类型 | 特点 |
|------|------|------|
| Alertmanager | 开源 | Prometheus 告警 |
| PagerDuty | 商业 | 事件响应平台 |
| Opsgenie | 商业 | Atlassian 生态 |

---

### CMDB 和资产管理 (跨价值流)

| 工具 | 类型 | 特点 |
|------|------|------|
| ServiceNow CMDB | 商业 | 企业级 CMDB |
| i-doit | 开源 | IT 文档和 CMDB |
| CMDBuild | 开源 | 可定制 CMDB |
| Snipe-IT | 开源 | IT 资产管理 |

---

## 集成架构

### 推荐集成模式

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        IT4IT Tool Integration Architecture                   │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  事件总线 (Event Bus)                                                        │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                         Apache Kafka                                 │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│       │           │           │           │           │           │        │
│       ▼           ▼           ▼           ▼           ▼           ▼        │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ │
│  │  Jira   │ │ GitLab  │ │ ArgoCD  │ │Prometheus│ │ServiceNow│ │  CMDB  │ │
│  │Portfolio│ │  CI/CD  │ │ Deploy  │ │ Monitor │ │  ITSM   │ │        │ │
│  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘ │
│       │           │           │           │           │           │        │
│       └───────────┴───────────┴───────────┴───────────┴───────────┘        │
│                                    │                                         │
│                                    ▼                                         │
│                           ┌─────────────────┐                               │
│                           │   Data Lake     │                               │
│                           │  (Analytics)    │                               │
│                           └─────────────────┘                               │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 关键集成点

| 源系统 | 目标系统 | 集成数据 | 方式 |
|-------|---------|---------|------|
| Jira | GitLab | Issue/MR 链接 | Webhook |
| GitLab | ArgoCD | 部署触发 | GitOps |
| ArgoCD | ServiceNow | 变更记录 | API |
| Prometheus | PagerDuty | 告警 | Webhook |
| PagerDuty | ServiceNow | 事件创建 | API |
| ServiceNow | CMDB | CI 更新 | Discovery |

---

## 选型建议

### 小型团队 (< 50 人)

```
推荐方案:
├── S2P: Jira + Confluence
├── D2F: GitLab (Community)
├── S2D: GitLab CI + ArgoCD + Terraform
└── C2R: Jira Service Management + Prometheus/Grafana
```

### 中型团队 (50-200 人)

```
推荐方案:
├── S2P: Jira Portfolio
├── D2F: GitLab (Premium) or GitHub Enterprise
├── S2D: GitLab CI + ArgoCD + Terraform + Ansible
└── C2R: ServiceNow (Express) + Datadog
```

### 大型企业 (> 200 人)

```
推荐方案:
├── S2P: ServiceNow SPM + Planview
├── D2F: Azure DevOps / GitLab Ultimate
├── S2D: Jenkins + Spinnaker + Terraform Enterprise
└── C2R: ServiceNow (Enterprise) + Splunk
```

---

## 迁移路径

### 从传统工具到现代工具链

```
阶段 1: 基础建设
├── 版本控制迁移到 Git
├── 建立 CI/CD 管道
└── 容器化应用

阶段 2: 自动化增强
├── 基础设施即代码
├── GitOps 部署
└── 自动化测试

阶段 3: 可观测性
├── 统一监控平台
├── 日志聚合
└── 分布式追踪

阶段 4: ITSM 集成
├── 自动化工单创建
├── 变更自动记录
└── CMDB 自动发现
```
