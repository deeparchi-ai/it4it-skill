# IT4IT Skill - 使用示例

## 示例 1：IT 服务管理体系设计

### 场景

需要为企业设计 IT 服务管理体系。

### 输入

"帮我基于 IT4IT 设计一个 IT 服务管理体系"

### 输出

```markdown
# IT 服务管理体系设计

## 1. 价值流架构

### 1.1 整体架构
```
┌─────────────────────────────────────────────────────────────────┐
│                    IT Service Management Architecture            │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   业务层                                                         │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │  Business Strategy  │  Business Demand  │  Business KPI  │   │
│   └─────────────────────────────────────────────────────────┘   │
│                              │                                   │
│   ════════════════════════════════════════════════════════════  │
│                                                                  │
│   IT 价值流层                                                    │
│   ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐          │
│   │   S2P   │─►│   D2F   │─►│   S2D   │─►│   C2R   │          │
│   │ 战略到   │  │ 设计到   │  │ 采购到   │  │ 消费到   │          │
│   │ 组合     │  │ 交付     │  │ 部署     │  │ 退役     │          │
│   └─────────┘  └─────────┘  └─────────┘  └─────────┘          │
│        │            │            │            │                 │
│   ════════════════════════════════════════════════════════════  │
│                                                                  │
│   工具层                                                         │
│   ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐          │
│   │Portfolio│  │ DevOps  │  │  CMDB   │  │ Service │          │
│   │  Mgmt   │  │ Platform│  │ + IaC   │  │  Desk   │          │
│   └─────────┘  └─────────┘  └─────────┘  └─────────┘          │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

### 1.2 功能组件清单

| 价值流 | 功能组件 | 工具选择 | 优先级 |
|-------|---------|---------|--------|
| S2P | Portfolio Demand Management | Jira Portfolio | P2 |
| S2P | Proposal Management | Confluence | P2 |
| D2F | Service Design | Archi/Draw.io | P1 |
| D2F | Service Development | GitLab | P1 |
| D2F | Service Release | GitLab CI | P1 |
| S2D | Build Package | Docker/K8s | P1 |
| S2D | Deploy Release | ArgoCD | P1 |
| S2D | Change Control | ServiceNow | P1 |
| C2R | Request Management | ServiceNow | P1 |
| C2R | Incident Management | ServiceNow | P1 |
| C2R | Problem Management | ServiceNow | P2 |
| C2R | Service Monitoring | Prometheus/Grafana | P1 |

## 2. 数据对象模型

### 2.1 服务主干设计

```
服务生命周期:

┌──────────────────┐
│ Conceptual       │  S2P: 业务需求阶段
│ Service          │  - 服务名称
│                  │  - 业务价值
│                  │  - 目标用户
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ Logical          │  D2F: 设计开发阶段
│ Service          │  - 服务架构
│                  │  - 技术规范
│                  │  - 接口定义
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ Actual           │  S2D: 部署运行阶段
│ Service          │  - 部署实例
│                  │  - 配置信息
│                  │  - 依赖关系
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ Service          │  C2R: 消费使用阶段
│ Contract         │  - SLA 定义
│                  │  - 使用约定
│                  │  - 计费规则
└──────────────────┘
```

### 2.2 核心数据对象

| 数据对象 | 属性 | 关联 |
|---------|------|------|
| Service | ID, Name, Description, Owner | Portfolio, Contract |
| Incident | ID, Priority, Status, Assignee | Service, CI |
| Change | ID, Type, Risk, Status | Service, CI, Release |
| CI | ID, Type, Status, Location | Service, Change |
| Release | ID, Version, Status, Date | Service, Change |

## 3. 流程设计

### 3.1 服务请求流程 (C2R)

```
用户 ─────► 服务目录 ─────► 请求提交 ─────► 审批
                                              │
                                              ▼
                                         自动/手工
                                           执行
                                              │
                                              ▼
用户 ◄───── 通知 ◄────── 完成确认 ◄──── 执行完成
```

### 3.2 变更管理流程 (S2D)

```
变更请求 ─► RFC记录 ─► 评估分类 ─► CAB审批
                                      │
    ┌─────────────────────────────────┤
    │                                 │
    ▼                                 ▼
 标准变更                          正常变更
    │                                 │
    ▼                                 ▼
 自动执行                          排期计划
    │                                 │
    ▼                                 ▼
 自动验证 ◄──────────────────── 实施验证
    │                                 │
    └────────────────┬────────────────┘
                     ▼
                变更关闭
```

## 4. 治理框架

### 4.1 角色和职责

| 角色 | 职责 | 价值流关联 |
|------|------|-----------|
| IT 战略负责人 | 制定 IT 战略，管理投资组合 | S2P |
| 服务设计师 | 设计服务架构和规范 | D2F |
| 发布经理 | 管理发布流程和变更 | S2D |
| 服务台经理 | 管理服务请求和事件 | C2R |
| 服务负责人 | 端到端服务生命周期 | 全部 |

### 4.2 KPI 指标

| 指标 | 定义 | 目标 |
|------|------|------|
| 服务可用性 | 服务正常运行时间比例 | ≥99.9% |
| 变更成功率 | 成功变更/总变更 | ≥95% |
| MTTR | 平均恢复时间 | ≤4h |
| 请求完成率 | 按时完成的请求比例 | ≥90% |
| 客户满意度 | 用户满意度评分 | ≥4.0/5.0 |
```

---

## 示例 2：DevOps 工具链设计

### 场景

需要基于 IT4IT 设计 DevOps 工具链。

### 输入

"帮我基于 IT4IT 设计 DevOps 工具链"

### 输出

```markdown
# DevOps 工具链设计 (IT4IT 视角)

## 1. IT4IT 到 DevOps 映射

### 1.1 价值流对应

| IT4IT 价值流 | DevOps 阶段 | 核心活动 |
|-------------|------------|---------|
| S2P | Plan | 需求管理、Sprint 规划 |
| D2F | Code, Build, Test | 编码、构建、测试 |
| S2D | Release, Deploy | 发布、部署、配置 |
| C2R | Operate, Monitor | 运维、监控、反馈 |

### 1.2 端到端工具链

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        DevOps Tool Chain (IT4IT Aligned)                     │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  S2P (Plan)                                                                  │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐                     │
│  │    Jira     │───►│ Confluence  │───►│   Miro      │                     │
│  │  Backlog    │    │    Wiki     │    │  Roadmap    │                     │
│  └─────────────┘    └─────────────┘    └─────────────┘                     │
│         │                                                                    │
│         ▼                                                                    │
│  D2F (Code → Build → Test)                                                  │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐                     │
│  │   GitLab    │───►│   GitLab    │───►│   GitLab    │                     │
│  │    Code     │    │     CI      │    │    SAST     │                     │
│  └─────────────┘    └─────────────┘    └─────────────┘                     │
│         │                 │                  │                              │
│         │                 ▼                  │                              │
│         │          ┌─────────────┐          │                              │
│         │          │   SonarQube │◄─────────┘                              │
│         │          │   Quality   │                                          │
│         │          └─────────────┘                                          │
│         │                                                                    │
│         ▼                                                                    │
│  S2D (Release → Deploy)                                                     │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐                     │
│  │   Harbor    │───►│   ArgoCD    │───►│ Kubernetes  │                     │
│  │  Registry   │    │   GitOps    │    │   Cluster   │                     │
│  └─────────────┘    └─────────────┘    └─────────────┘                     │
│         │                 │                  │                              │
│         │                 ▼                  │                              │
│         │          ┌─────────────┐          │                              │
│         │          │  Terraform  │──────────┘                              │
│         │          │     IaC     │                                          │
│         │          └─────────────┘                                          │
│         │                                                                    │
│         ▼                                                                    │
│  C2R (Operate → Monitor)                                                    │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐                     │
│  │ Prometheus  │───►│   Grafana   │───►│   PagerDuty │                     │
│  │   Metrics   │    │  Dashboard  │    │   Alerting  │                     │
│  └─────────────┘    └─────────────┘    └─────────────┘                     │
│         │                                      │                            │
│         ▼                                      ▼                            │
│  ┌─────────────┐                        ┌─────────────┐                     │
│  │    Loki     │                        │ ServiceNow  │                     │
│  │    Logs     │                        │   ITSM      │                     │
│  └─────────────┘                        └─────────────┘                     │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 2. 工具选型

### 2.1 按功能组件选型

| IT4IT 功能组件 | 推荐工具 | 替代方案 |
|---------------|---------|---------|
| Portfolio Demand | Jira | Azure Boards |
| Service Design | Archi, Draw.io | Sparx EA |
| Service Development | GitLab | GitHub, Bitbucket |
| Build Package | Docker, Buildah | Podman |
| Deploy Release | ArgoCD | Flux, Spinnaker |
| Change Control | GitLab MR | ServiceNow |
| Service Monitoring | Prometheus + Grafana | Datadog |
| Incident Management | PagerDuty + ServiceNow | Opsgenie |
| CMDB | ServiceNow | i-doit |

### 2.2 集成架构

```
┌─────────────────────────────────────────────────────────────────┐
│                    Integration Architecture                      │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  事件总线 (Event Bus)                                            │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │                    Apache Kafka                          │   │
│  └─────────────────────────────────────────────────────────┘   │
│        │         │          │          │          │             │
│        ▼         ▼          ▼          ▼          ▼             │
│  ┌─────────┐┌─────────┐┌─────────┐┌─────────┐┌─────────┐      │
│  │  Jira   ││ GitLab  ││ ArgoCD  ││Prometheus││ServiceNow│      │
│  └─────────┘└─────────┘└─────────┘└─────────┘└─────────┘      │
│                                                                  │
│  API 网关                                                        │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │                    Kong / API Gateway                    │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

## 3. 数据流设计

### 3.1 CI/CD 数据流

```
Code Commit
    │
    ▼
┌───────────────┐
│ Build Event   │ ──► Kafka ──► Dashboard
│ (GitLab CI)   │              (Grafana)
└───────┬───────┘
        │
        ▼
┌───────────────┐
│ Test Results  │ ──► Kafka ──► Quality Gate
│ (SonarQube)   │              (SonarQube)
└───────┬───────┘
        │
        ▼
┌───────────────┐
│ Image Push    │ ──► Kafka ──► Security Scan
│ (Harbor)      │              (Trivy)
└───────┬───────┘
        │
        ▼
┌───────────────┐
│ Deploy Event  │ ──► Kafka ──► CMDB Update
│ (ArgoCD)      │              (ServiceNow)
└───────┬───────┘
        │
        ▼
┌───────────────┐
│ Health Check  │ ──► Kafka ──► Incident
│ (Prometheus)  │              (PagerDuty)
└───────────────┘
```

## 4. 实施路线图

### Phase 1: 基础设施 (Month 1-2)
- Kubernetes 集群部署
- GitLab 安装配置
- Harbor 镜像仓库

### Phase 2: CI/CD 管道 (Month 3-4)
- GitLab CI 配置
- ArgoCD GitOps 部署
- SonarQube 集成

### Phase 3: 监控告警 (Month 5-6)
- Prometheus + Grafana
- Loki 日志系统
- PagerDuty 告警集成

### Phase 4: ITSM 集成 (Month 7-8)
- ServiceNow 集成
- 自动化事件创建
- 变更自动记录
```

---

## 示例 3：CMDB 数据模型设计

### 场景

需要基于 IT4IT 设计 CMDB 数据模型。

### 输入

"帮我基于 IT4IT 设计 CMDB 数据模型"

### 输出

```markdown
# CMDB 数据模型设计 (IT4IT 对齐)

## 1. 数据模型概览

### 1.1 CI 类型层次

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                           CMDB Data Model                                    │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  服务层 (Service Layer) - IT4IT Service Backbone                            │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                                                                      │   │
│  │  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐          │   │
│  │  │  Business    │───►│  Technical   │───►│  Service     │          │   │
│  │  │  Service     │    │  Service     │    │  Instance    │          │   │
│  │  └──────────────┘    └──────────────┘    └──────────────┘          │   │
│  │                                                                      │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                              │                                               │
│                              ▼                                               │
│  应用层 (Application Layer)                                                  │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                                                                      │   │
│  │  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐          │   │
│  │  │ Application  │───►│  Component   │───►│   Module     │          │   │
│  │  └──────────────┘    └──────────────┘    └──────────────┘          │   │
│  │                                                                      │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                              │                                               │
│                              ▼                                               │
│  基础设施层 (Infrastructure Layer)                                          │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                                                                      │   │
│  │  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐          │   │
│  │  │   Server     │    │   Database   │    │   Network    │          │   │
│  │  └──────────────┘    └──────────────┘    └──────────────┘          │   │
│  │         │                   │                   │                   │   │
│  │         ▼                   ▼                   ▼                   │   │
│  │  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐          │   │
│  │  │   Virtual    │    │   Storage    │    │   Firewall   │          │   │
│  │  │   Machine    │    │              │    │              │          │   │
│  │  └──────────────┘    └──────────────┘    └──────────────┘          │   │
│  │                                                                      │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 2. CI 类型定义

### 2.1 服务类

#### Business Service
```yaml
CI Type: Business Service
Description: 面向业务的服务定义
Attributes:
  - service_id: string (PK)
  - name: string
  - description: text
  - owner: string
  - status: enum [Active, Inactive, Retired]
  - criticality: enum [High, Medium, Low]
  - sla_id: string (FK)
Relationships:
  - contains: Technical Service (1:N)
  - consumed_by: Business Unit (N:M)
  - supported_by: Support Group (N:M)
```

#### Technical Service
```yaml
CI Type: Technical Service
Description: 技术实现的服务
Attributes:
  - service_id: string (PK)
  - name: string
  - version: string
  - type: enum [API, Web, Batch, Streaming]
  - status: enum [Development, Staging, Production, Deprecated]
  - environment: string
Relationships:
  - realizes: Business Service (N:1)
  - deployed_on: Application (N:M)
  - depends_on: Technical Service (N:M)
```

### 2.2 应用类

#### Application
```yaml
CI Type: Application
Description: 应用系统
Attributes:
  - app_id: string (PK)
  - name: string
  - version: string
  - technology_stack: string
  - repository_url: string
  - owner: string
  - status: enum [Active, Maintenance, EOL]
Relationships:
  - hosts: Technical Service (N:M)
  - contains: Component (1:N)
  - runs_on: Server/Container (N:M)
  - uses: Database (N:M)
```

### 2.3 基础设施类

#### Server
```yaml
CI Type: Server
Description: 物理或虚拟服务器
Attributes:
  - server_id: string (PK)
  - hostname: string
  - ip_address: string
  - os_type: string
  - os_version: string
  - cpu_cores: integer
  - memory_gb: integer
  - location: string
  - status: enum [Running, Stopped, Maintenance]
Relationships:
  - hosts: Application (N:M)
  - connected_to: Network (N:M)
  - uses: Storage (N:M)
```

## 3. 关系类型

| 关系类型 | 描述 | 示例 |
|---------|------|------|
| Contains | 包含关系 | Application contains Components |
| Runs On | 运行于 | Application runs on Server |
| Depends On | 依赖 | Service A depends on Service B |
| Connected To | 连接 | Server connected to Network |
| Uses | 使用 | Application uses Database |
| Realizes | 实现 | Technical Service realizes Business Service |

## 4. IT4IT 数据对象映射

| IT4IT 数据对象 | CMDB CI 类型 | 说明 |
|---------------|-------------|------|
| Conceptual Service | Business Service | 业务视角服务 |
| Logical Service | Technical Service | 技术设计 |
| Actual Service | Service Instance | 运行实例 |
| Configuration Item | All CI Types | 通用 CI |
| Release Package | Release | 发布包 |
| Change Record | Change | 变更记录 |

## 5. 自动发现集成

```
┌─────────────────────────────────────────────────────────────────┐
│                    Auto-Discovery Architecture                   │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐         │
│  │ Kubernetes  │    │   Cloud     │    │  Network    │         │
│  │   API       │    │   API       │    │  Scanner    │         │
│  └──────┬──────┘    └──────┬──────┘    └──────┬──────┘         │
│         │                  │                  │                 │
│         └──────────────────┼──────────────────┘                 │
│                            ▼                                     │
│                   ┌─────────────────┐                           │
│                   │  Discovery      │                           │
│                   │  Engine         │                           │
│                   └────────┬────────┘                           │
│                            │                                     │
│                            ▼                                     │
│                   ┌─────────────────┐                           │
│                   │  Reconciliation │                           │
│                   │  Engine         │                           │
│                   └────────┬────────┘                           │
│                            │                                     │
│                            ▼                                     │
│                   ┌─────────────────┐                           │
│                   │     CMDB        │                           │
│                   └─────────────────┘                           │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```
```

---

## 示例 4：IT 运营模型设计

### 场景

需要基于 IT4IT 设计 IT 运营模型。

### 输入

"帮我设计基于 IT4IT 的 IT 运营模型"

### 输出

```markdown
# IT 运营模型设计

## 1. 运营模型概览

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         IT Operating Model                                   │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  战略层                                                                      │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  IT Strategy  │  Portfolio Mgmt  │  Governance  │  Enterprise Arch  │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                      │                                       │
│  ════════════════════════════════════════════════════════════════════════  │
│                                                                              │
│  交付层                                                                      │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                                                                      │   │
│  │  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐             │   │
│  │  │  Product    │    │  Platform   │    │   Shared    │             │   │
│  │  │  Teams      │    │   Team      │    │  Services   │             │   │
│  │  │             │    │             │    │             │             │   │
│  │  │ • Feature   │    │ • DevOps    │    │ • Security  │             │   │
│  │  │ • Delivery  │    │ • SRE       │    │ • Data      │             │   │
│  │  │ • Support   │    │ • Cloud     │    │ • Testing   │             │   │
│  │  └─────────────┘    └─────────────┘    └─────────────┘             │   │
│  │                                                                      │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                      │                                       │
│  ════════════════════════════════════════════════════════════════════════  │
│                                                                              │
│  运营层                                                                      │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  Service Desk  │  NOC/SOC  │  Change Mgmt  │  Problem Mgmt          │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 2. 价值流团队职责

| 价值流 | 团队 | 职责 |
|-------|------|------|
| S2P | Strategy & Portfolio | IT 战略、投资组合、架构治理 |
| D2F | Product Teams | 产品开发、服务设计、质量保证 |
| S2D | Platform Team | CI/CD、基础设施、部署自动化 |
| C2R | Operations | 服务台、监控、事件管理 |

## 3. 关键流程

### 3.1 需求到交付

```
业务需求 ──► 需求分析 ──► 优先级排序 ──► Sprint 规划
                                              │
                                              ▼
                                         开发测试
                                              │
                                              ▼
发布上线 ◄── 部署准备 ◄── 发布审批 ◄── 验收测试
```

### 3.2 事件到恢复

```
告警/报告 ──► 事件记录 ──► 分类分派 ──► 诊断处理
                                              │
                                              ▼
                                         恢复服务
                                              │
                                              ▼
关闭归档 ◄── 用户确认 ◄── 验证测试 ◄── 根因分析
```

## 4. 度量体系

| 类别 | 指标 | 目标 | 数据来源 |
|------|------|------|---------|
| 价值 | 需求交付周期 | ≤30天 | Jira |
| 质量 | 变更成功率 | ≥95% | ServiceNow |
| 效率 | 部署频率 | ≥1次/天 | GitLab |
| 稳定 | 服务可用性 | ≥99.9% | Prometheus |
| 响应 | MTTR | ≤4小时 | ServiceNow |
```

这些示例展示了 IT4IT Skill 在不同场景下的应用，包括 IT 服务管理体系设计、DevOps 工具链、CMDB 数据模型和 IT 运营模型设计。
