---
name: personalization-weekly-review
description: Use when reviewing a week's collaboration to identify stable personalization changes, resolve repeated corrections or rework, audit existing preferences, or decide whether an instruction belongs in global preferences, a project rule, a skill, or memory.
---

# 个性化周度复盘 / Personalization Weekly Review

## 目标 / Purpose

将一周协作中可验证的重复模式沉淀为**候选建议**，而非自动扩充个性化设置。Use the approved baseline as the comparison source and keep one-off facts, temporary instructions, and project constraints out of global preferences.

## 输入与真源 / Inputs and source of truth

1. Read `PERSONALIZATION_BASELINE.md` and `CANDIDATE_POOL.md` first.
2. Review only the supplied conversations, project records, and user corrections; do not invent frequency, evidence, or user intent.
3. Treat the baseline as the current formal truth. If new material conflicts with it, report the conflict and request confirmation rather than silently replacing it.

## 提取信号 / Signals to examine

| 信号 / Signal | 判断重点 / What to assess |
|---|---|
| 明确长期要求 / explicit long-term request | Does the user clearly state that it should recur across contexts? |
| 用户纠正 / correction | Was a fact, term, metric, scope, or communication preference corrected? |
| 返工 / rework | What root cause made the earlier result unusable? |
| 重复提醒 / repeated reminder | Is the same behavior recurring with enough evidence to be stable? |
| 成功模式 / successful pattern | Was a response or workflow repeatedly useful and context-independent? |
| 既有规则失效 / existing-rule failure | Is the rule absent, unclear, ignored, or duplicated? |

For a correction or rework event, check same-class locations and affected summaries, metrics, tables, conclusions, or attachments. Record the root cause; do not merely repair the most visible sentence.

## 分层决策 / Placement decision

| 去向 / Destination | Use when | Do not use when |
|---|---|---|
| Global personalization | Stable, cross-project collaboration preference with evidence | A single incident or a project fact |
| Domain rule | Recurring requirement of a work type, such as acceptance reporting | It applies only to one project |
| Project rule | Confirmed scope, terminology, metric definition, or local workflow | It should guide unrelated work |
| Skill / SOP | A repeatable procedure needs an execution workflow | It is just a preference or factual state |
| Memory / state | A durable fact, decision, or current status | It is a behavioral instruction |
| Do not persist | Temporary authorization, emergency instruction, unverified idea, or one-off request | Repeated evidence supports a stable rule |

## 复盘方法 / Review method

1. Give a one-sentence weekly judgment.
2. Build a signal table: event, evidence, frequency/time range if known, root cause, scope, confidence, and recommended destination.
3. Audit baseline health: retain, clarify, merge, retire, or observe. Prefer amending a weak existing rule over adding a duplicate.
4. List proposals under **Add / Modify / Remove / Observe / Do not persist**.
5. State evidence gaps and the next smallest action needed to resolve them.

## 证据与验收边界 / Evidence and acceptance boundary

For acceptance-report or technical-project work, maintain this chain:

`acceptance requirement → metric definition → counting method → raw material/data → test or proof → conclusion`

Separate facts, engineering inferences, and future targets. The existence of a document, configuration, code, or static check proves only that artifact exists. State the actual verification level—design formed, implementation/configuration present, single-function tested, end-to-end tested, real-data tested, or repeated/stability tested—and label missing evidence as pending, uncollected, unverified, or insufficient.

## 输出模板 / Output template

```markdown
# Personalization Weekly Review / 个性化周度复盘
Week / 周次：YYYY-Www

## 1. 一句话判断 / One-sentence judgment

## 2. 高价值信号 / High-value signals
| Signal | Evidence | Root cause | Scope | Confidence | Recommended destination |

## 3. 现有规则健康检查 / Baseline health check

## 4. 候选建议 / Candidates
### Add / 新增
### Modify / 修改
### Remove / 删除
### Observe / 继续观察
### Do not persist / 不沉淀

## 5. 证据缺口与下一步 / Evidence gaps and next step
```

## 变更控制 / Change control

- Never edit `PERSONALIZATION_BASELINE.md` automatically.
- Add or update a candidate in `CANDIDATE_POOL.md`; include evidence, scope, confidence, status, and next review action.
- Apply a baseline change only after explicit human approval. Update `CHANGELOG.md` in the same approved change.
- Do not generalize a correction beyond its evidence. Do not convert a temporary request into a permanent rule.
- When the user corrects an established fact, term, metric, or state, treat the latest confirmed correction as current truth and check relevant same-class content.
