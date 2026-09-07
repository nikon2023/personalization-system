# 个性化候选池 / Personalization Candidate Pool

> 目的 / Purpose: 记录待观察或待批准的个性化变更，避免一次性情况直接进入基线。  
> 当前状态 / Current state: 初始化时无待处理候选 / No pending candidates at initialization.

## 候选状态 / Candidate states

| 状态 / Status | 含义 / Meaning |
|---|---|
| Observe / 观察 | 证据不足，继续收集跨情境或重复信号。 |
| Proposed / 待批准 | 证据足以提出正式建议，等待用户明确决定。 |
| Adopted / 已采纳 | 已获批准，且基线与变更日志已同步更新。 |
| Rejected / 已否决 | 已决定不纳入；保留理由，避免重复提出。 |
| Retired / 已退役 | 曾有效但已不再适用的规则或候选。 |

## 候选记录模板 / Candidate record template

```markdown
## P-YYYY-NNN — 简短名称 / Short name

- Status / 状态：Observe | Proposed | Adopted | Rejected | Retired
- Proposed destination / 建议去向：Global personalization | Domain rule | Project rule | Skill/SOP | Memory/state | Do not persist
- Observation / 现象：
- Evidence / 证据：来源、日期、次数或时间范围；未知时明确写“未采集”。
- Root cause / 根因：
- Scope / 适用范围：跨项目、领域内、单项目或一次性。
- Confidence / 置信度：High | Medium | Low，并说明依据。
- Relationship to baseline / 与基线关系：新增、澄清、合并、替换或不适用。
- Decision / 决定：仅在用户明确确认后填写。
- Next review action / 下次复核动作：
```

## 记录规则 / Recording rules

1. 没有证据时不将候选提升为全局规则；写明“未采集”或“待补充”。
2. 单次纠正先判断其是否为项目事实、临时事项或局部表述，不自动推广。
3. 已采纳候选必须在 `PERSONALIZATION_BASELINE.md` 和 `CHANGELOG.md` 中有对应记录。
4. 已否决和已退役候选保留简要原因，避免以后把相同情况再次当作新发现。
