# CMC Forge — Claude Code 医药 CMC 专项 Skill

> 从候选分子到上市后，把 CMC 工作变成可管理、可追溯、可交付的结构化项目。

## 这是什么？

CMC Forge 是一个 Claude Code Skill，为制药/生物制药 CMC 专业人员提供：

- **文档起草** — PPQ 方案、Module 3 骨架、可比性策略、技术转移工作包
- **风险评估** — 成药性评估、IND 前差距分析、变更影响评估
- **项目规划** — 阶段门工作包、证据地图、交付物分解
- **培训设计** — FAQ、培训大纲、知识资产结构化
- **中国 + 国际化 CMC 路线图** — CDE/NMPA 申报、出海 FDA/EMA 准备、双语术语控制、global core package + regional delta

## 四种工作模式

| 模式 | 用途 | 典型请求 |
|------|------|---------|
| **DRAFT** | 起草 CMC 文档 | "帮我起草 PPQ 方案"、"搭 Module 3 骨架" |
| **ASSESS** | 风险/差距评估 | "做 IND 前 CMC readiness"、"评估这个变更的影响" |
| **PLAN** | 项目/工作包规划 | "做 tech transfer 工作包"、"搭 BLA 申报工作计划" |
| **TRAIN** | 培训/知识资产 | "设计工艺变更培训"、"整理 CMC FAQ" |

## 快速开始

### 1. 告诉 Claude 你的项目背景

```
药物类型：单抗 / 双抗 / ADC / 融合蛋白 / 小分子 / CGT
开发阶段：Pre-IND / Phase I / Phase II / Phase III / BLA / 上市后
目标区域：CDE/NMPA / FDA / EMA / PMDA / 多区域
企业姿态：中国申报 / 中国先行后出海 / 全球包桥接中国 / 海外品种本地化
```

### 2. 发出请求

```
# 起草文档
帮我起草一份 mAb 的 PPQ Protocol 框架，500L 规模，3 批连续生产

# 评估风险
帮我做 IND 前 CMC readiness assessment，单抗冻干制剂，2 批毒理批 + 1 批临床试制

# 规划项目
帮我把 mAb 工艺转给 CDMO 的 tech transfer 工作包搭起来

# 设计培训
把"工艺变更与 comparability"转成 60 分钟培训 + FAQ

# 中国先行 + 国际化
我们是一家中国 Biotech，单抗项目先走 CDE IND，两年后希望支持 FDA IND。请搭一版 CMC evidence roadmap，区分 global core package、CDE delta、FDA delta 和 90 天行动项
```

### 3. 先看骨架，再展开

CMC 文档通常很长。最佳实践：先让 Claude 生成大纲/框架，确认后再逐节展开。

## 合规红线

CMC Forge 是**起草工具**，不是审批系统：
- ✅ 帮你起草 PPQ 方案、可比性策略、Module 3 骨架
- ✅ 帮你识别风险、缺口、优先级
- ❌ 不能批准偏差、放行批次、签发 GMP 记录
- ❌ 不能编造数据、规格、验证结果

所有受监管文档输出均标注 `Draft for controlled review`。

## 项目结构

```
cmc-forge/
├── SKILL.md                          # 主技能文件（4 模式工作流）
├── playbooks/                        # 领域知识脚本
│   ├── druggability-assessment.md    # 成药性评估（4维+红绿灯）
│   ├── early-prioritization.md       # 早期模块优先级（P0-P4）
│   ├── risk-comparability.md         # 风险管理+可比性三步法
│   ├── compliance-continuum.md       # 全生命周期合规连续体
│   ├── gmp-qa-principles.md          # GMP/QA 基础与偏差管理
│   └── content-structuring.md        # 培训内容结构化方法
├── references/                       # 操作指引
│   ├── routing.md                    # 请求路由（5条路线）
│   ├── project-archetypes.md         # 项目原型分类（7+2+2）
│   ├── deliverable-patterns.md       # 6种交付物模式
│   ├── gxp-boundaries.md             # GxP 边界与安全使用
│   ├── regulatory-anchors.md         # 法规锚点（ICH/FDA/NMPA）
│   ├── china-global-cmc-operating-model.md  # 中国企业国际化 CMC 工作模型
│   └── quality-checklist.md          # CMC 文档质量检查清单
├── templates/                        # 文档模板
│   ├── process-validation-protocol-framework.md  # PPQ 方案
│   ├── module3-workplan-template.md              # Module 3 工作计划
│   ├── stage-gate-readiness-template.md          # 阶段门就绪包
│   ├── tech-transfer-template.md                 # 技术转移工作包
│   └── change-comparability-template.md          # 变更与可比性
├── examples/                         # 完整示例输出
│   ├── candidate-assessment-example.md  # 双抗候选评估示例
│   └── process-change-example.md        # 树脂变更评估示例
└── evals/
    └── evals.json                    # 8 个评估场景
```

## 与其他 Skill 的配合

| Skill | 关系 |
|-------|------|
| **scientific-writer** | CMC Forge 起草内容后，用 scientific-writer 做 5-pass 写作质量审核 |
| **Pharmacy_CMC** | 知识库层：42 章ICH/NMPA/CTD 知识供深度查询 |

## 适用场景

- IND/BLA/NDA 申报的 CMC 准备
- 工艺验证（PPQ）方案起草
- 技术转移工作包规划
- 工艺变更影响评估与可比性策略
- Module 3 (CTD) 骨架搭建与内容管理
- 分析方法生命周期规划
- CMC 团队培训与知识体系建设
- 监管会议准备（pre-IND, EOP2, pre-BLA）
- 中国创新药出海、海外品种转中国本地生产、跨区域 CMC evidence roadmap

## 版本

- **v2.1 (cmc-forge)**: 增强中国医药企业国际化场景，新增 China + Global CMC Operating Model、区域 delta 输出、双语术语控制、ICH Q2(R2)/Q14/Q5A(R2) 更新与新增评估场景
- **v2.0 (cmc-forge)**: 重构为 4 模式架构，充实模板和示例，新增质量检查清单，扩展 GMP/QA playbook，新增 NMPA 法规锚点
- **v1.0 (pharmasee_CMC)**: 初始版本，6 个 playbook + 5 个参考文件 + 5 个模板
