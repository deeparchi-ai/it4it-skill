---
name: it4it
version: 1.0.0
description: IT4IT Reference Architecture for managing the business of IT. Provides value chain framework with four value streams (S2P, D2F, S2D, C2R), functional components, data object model, and implementation guidance. Use this skill for IT service management, IT operations modeling, DevOps integration, or any IT management architecture work.
author: DeepArchi
license: MIT
keywords:
  - it4it
  - it-management
  - value-stream
  - itsm
  - devops
  - service-management
  - deeparchi
---

# IT4IT Skill - IT 管理参考架构

## 概述

IT4IT 是 The Open Group 发布的 IT 管理参考架构，为管理 IT 业务提供了规范性的框架。

## 何时使用

当用户需要：
- 了解或应用 IT4IT 参考架构
- 设计 IT 服务管理体系
- 优化 IT 价值链和价值流
- 选择和集成 IT 管理工具
- 建立 IT 运营模型
- 实施 DevOps 和敏捷 IT

## 快速开始

1. 参考 `README.md` 了解 IT4IT 核心概念
2. 查看 `references/value-stream-guide.md` 了解四大价值流
3. 使用 `assets/it4it-value-chain.drawio` 作为参考
4. 参考 `references/tool-mapping-guide.md` 选择工具

## 核心功能

- **价值链框架**：端到端 IT 管理视图
- **四大价值流**：S2P, D2F, S2D, C2R
- **功能组件**：20+ 标准功能组件
- **数据对象模型**：服务主干和支撑对象
- **工具映射**：常见工具对应关系
- **实施指南**：渐进式实施路径

## 价值流速查

```
S2P (Strategy to Portfolio)
  目标: 业务战略 → IT 投资组合
  关键输出: Conceptual Service, IT Portfolio

D2F (Design to Fulfill)
  目标: 需求 → IT 服务
  关键输出: Logical Service, Service Release

S2D (Source to Deploy)
  目标: 采购 → 部署
  关键输出: Actual Service, Configuration Items

C2R (Consume to Retire)
  目标: 消费 → 退役
  关键输出: Service Contract, Usage Data
```

## 服务主干

```
Conceptual Service → Logical Service → Actual Service → Service Contract
     (S2P)              (D2F)             (S2D)            (C2R)
```

## 资源文件

- `README.md` - 完整技能文档
- `EXAMPLES.md` - 使用示例
- `assets/it4it-value-chain.drawio` - 价值链图
- `references/value-stream-guide.md` - 价值流指南
- `references/data-object-model.md` - 数据对象模型
- `references/tool-mapping-guide.md` - 工具映射指南
- `scripts/validate-it4it.js` - 验证脚本

## 相关链接

- [IT4IT Official Website](https://www.opengroup.org/it4it)
- [The Open Group](https://www.opengroup.org/)
- [DeepArchi 架构管理平台](https://deeparchi.com)
