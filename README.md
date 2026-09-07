# 个性化系统迁移包 / Personalization System

一个可移植的个人协作治理包：用每周复盘发现稳定模式，用候选池控制变更，用正式基线保留已确认偏好。

A portable personal-collaboration governance package: weekly reviews discover stable patterns, the candidate pool controls changes, and the formal baseline preserves approved preferences.

## 文件清单 / Contents

| 文件 / File | 作用 / Role |
|---|---|
| `SKILL.md` | 周度复盘方法、证据要求与分层决策 / weekly review method, evidence rules, placement decisions |
| `PERSONALIZATION_BASELINE.md` | 已确认的全局协作原则与表达偏好 / approved cross-project principles and response preferences |
| `CANDIDATE_POOL.md` | 待观察、待批准及已处置候选 / observed, proposed, and resolved candidates |
| `CHANGELOG.md` | 经批准的变动记录 / approved-change record |
| `README.md` | 安装、初始化与维护说明 / installation, initialization, and maintenance guide |

## 安装 / Install

1. Clone or download this private repository to the environment where you want to reuse it.
2. For Codex-style skills, place the package folder in the environment's discoverable skills location, keeping `SKILL.md` at the package root.
3. Keep the baseline, candidate pool, and changelog beside the Skill; they are its governance state, not optional examples.
4. Read the baseline before the first review. Do not overwrite it with assumptions from a new environment.

## 首次初始化 / First use

1. Confirm that `PERSONALIZATION_BASELINE.md` reflects only cross-project, stable preferences.
2. Move project-specific facts and requirements to the relevant project material; do not copy them into the baseline.
3. Leave `CANDIDATE_POOL.md` empty until there is evidence for a candidate.
4. Record the migration or approved adjustment in `CHANGELOG.md`.

## 每周使用 / Weekly use

1. Provide the week’s relevant conversation, correction, rework, and project-context material.
2. Invoke `personalization-weekly-review` or follow `SKILL.md`.
3. Review the output’s Add, Modify, Remove, Observe, and Do not persist sections.
4. Approve, reject, or defer each proposed change explicitly.
5. Only after approval: update the baseline, candidate pool, and changelog together.

## 变更与回滚 / Change and rollback

- The weekly review never modifies the baseline automatically.
- To roll back an approved rule, restore the prior text through version control, mark the corresponding candidate `Retired` or `Rejected`, and add a dated changelog entry explaining why.
- If evidence is incomplete, retain the candidate as `Observe` and state what would establish or reject it.

## 验收报告协作边界 / Acceptance-report boundary

本包支持验收报告协作，但不会替代项目任务书、原始数据或测试材料。任何验收结论必须回到“要求—定义—统计口径—原始材料—测试/证明—结论”的证据链，并如实标明未验证部分。

This package supports acceptance-report collaboration; it does not replace a project charter, raw data, or test material. Every acceptance conclusion must trace back to the requirement-definition-counting-method-raw-material-test-or-proof-conclusion chain and identify unverified parts honestly.
