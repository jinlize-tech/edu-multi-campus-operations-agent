---
name: edu-multi-campus-operations-agent-core
display_name: '多校区运营协同核心助手'
display_name_en: 'Multi Campus Operations Agent Core Assistant'
description: '为多校区运营协同提供输入校验、结构化整理和成果模板支持'
description_zh: '校验各校区经营/招生/教学/教务/服务数据、资源、流程和协同问题的完整性，并整理为可交付结构'
description_en: 'Validate structured inputs and prepare an output-ready structure for the parent agent.'
examples_zh:
  - '检查我提交的输入字段是否完整'
  - '整理这份业务资料并标出冲突项'
examples_en:
  - 'Check whether my structured input is complete.'
  - 'Organize the supplied business information and flag conflicts.'
version: 1.0.2
author: '广州金励泽科技服务有限公司'
---

# 多校区运营协同核心助手

本Skill是Agent内部的结构化支持组件，不替代Agent的诊断、方案设计、人工确认和复盘职责。

## 产品契约

- 核心任务：多校区运营分析和管理协同。
- 主要风险：数据不可比、跨校区隐私和控制权限不清
- 去重边界：与校长经营OS LITE区分：多校区运营分析，不提供完整经营系统；与校区标准化Agent区分偏运营协同而非标准体系。

## 输入

- 各校区经营/招生/教学/教务/服务数据
- 资源
- 流程和协同问题

## 工作流程

1. 用户提供结构化JSON时，先执行 @scripts/validate_input.js。
2. 输入缺失时返回缺失字段，不要求Agent自行编造。
3. 输入冲突时返回确认项，暂停正式结论。
4. 安全检查通过后，按 @templates/OUTPUT_TEMPLATE.md 建立空结构。
5. 将结构交回Agent继续专业处理。

## 专属检查

- 先明确标准版本、适用校区、检查范围、证据来源和例外条件。
- 按流程节点核对责任人、输入、完成标准、输出和升级机制。
- 区分现状证据、标准要求、差距、影响、整改动作和复验标准。
- 不代替机构作出处罚、人事、财务或行政批准决定。

## 边界

不得代替机构作出处罚或人事决定，不得把检查结果等同于行政批准。

本Skill不产生最终业务结论，不调用外部收费API，不保存用户数据。
