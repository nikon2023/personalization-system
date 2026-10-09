# 变更日志 / Changelog

本日志仅记录经用户明确批准的基线或包结构变动。日期采用 `YYYY-MM-DD`，每项记录应说明原因、证据范围与影响文件。

This log records only baseline or package-structure changes explicitly approved by the user. Dates use `YYYY-MM-DD`; each entry states rationale, evidence scope, and affected files.

## [1.1.0] — 2026-10-09

### Added / 新增

- 新增 `understand-first` Skill。
- Added the `understand-first` Human–AI problem-solving skill.
- 新增中英文 README，说明三类思想来源、调用方式、Representation Ladder、Evidence Gate 与能力沉淀逻辑。
- Added bilingual READMEs documenting sources, invocation, representation escalation, evidence checking, and capability transfer.
- 根 README 增加 Skill 索引和调用入口。
- Added the new skill to the root README index.

### Design boundary / 设计边界

- Reddit Prompt 仅作为前置诊断来源，不默认改写其核心结构。
- The Reddit prompt is treated as the canonical preflight source rather than silently rewritten.
- 陶哲轩访谈用于定义“正确输出不等于理解”的目标启发；`Pattern → Root Cause → Verification → Transfer` 是本 Skill 的工程化提炼，不作为陶哲轩原话。
- Tao's interview motivates the understanding goal; `Pattern → Root Cause → Verification → Transfer` is this skill's synthesis, not a direct quotation.
- Karpathy 的 STE-style text → diagram → interactive web → explainer video 被用作表达升级梯子。
- Karpathy's representation sequence is used as an escalation ladder, not as a requirement to generate all four formats.

### Affected files

- `skills/understand-first/SKILL.md`
- `skills/understand-first/README.md`
- `skills/understand-first/README.zh-CN.md`
- `README.md`
- `CHANGELOG.md`

## [1.0.0] — 2026-09-07

### 初始化 / Initial release

- 建立个性化周度复盘 Skill、正式协作基线、候选池、变更日志与使用说明。
- Established the weekly-review skill, formal collaboration baseline, candidate pool, changelog, and operating guide.

### 依据与边界 / Basis and boundary

- 依据：当前已确认的周度个性化复盘、自进化、验收报告协作与分层治理原则。
- Evidence scope: confirmed principles for weekly personalization review, controlled evolution, acceptance-report collaboration, and layered governance.
- 影响文件 / Affected files: all five initial package files.
- 未包含项目专属事实、凭据或未经验证的能力结论。No project-specific facts, credentials, or unverified capability claims are included.
