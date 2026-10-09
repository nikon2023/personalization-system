---
name: understand-first
description: >
  Use when a question is ambiguous, strategic, analytical, repeatedly blocked, or likely to become a reusable rule.
  Diagnose before answering, optimize for human understanding rather than answer volume, use the lowest effective
  representation rung, verify important claims, and extract reusable capability candidates. Preserve the canonical
  preflight prompt unless the user explicitly changes it.
---

# Understand First / 先理解，再回答

## Purpose

This skill helps a human and an AI solve a problem together.

It does not optimize only for producing an answer.

It optimizes for four outcomes:

1. See the pattern.
2. Identify the root cause.
3. Verify the result.
4. Transfer the learning into a reusable capability.

Use the smallest amount of process that improves the answer.

Do not force the full protocol on simple questions.

## Source model

This skill combines three independent ideas.

### A. Canonical preflight prompt

The preflight comes from a widely shared Reddit prompt pattern.

Its role is to expose hidden assumptions, missing information, and common failure modes before the model commits to an answer.

Do not rewrite or "improve" the canonical preflight by default.

### B. Understanding as the goal

Terence Tao's 2026 discussions of AI and mathematics emphasize that a correct result is not the same as human understanding.

The human still needs to evaluate, explain, connect, and internalize results.

This skill translates that principle into four operational checks:

`pattern → root cause → verification → transfer`

This four-part check is this skill's synthesis. It is not a quotation from Tao.

### C. Representation ladder

Andrej Karpathy's 2 October 2026 post proposes increasingly rich formats for understanding model output:

`STE-style text → diagram → interactive web page → explainer video`

This skill treats the ladder as an escalation mechanism.

Use the lowest rung that resolves the cognitive block.

Clearer presentation never replaces verification.

# 1. Canonical Preflight

For ambiguous, strategic, analytical, or repeatedly blocked questions, use this block before the final answer.

Preserve its intent and order.

> Don't answer my question yet.
>
> First do this:
>
> 1. Tell me what assumptions I'm making that I haven't stated out loud.
> 2. Tell me what information would significantly change your answer if you had it.
> 3. Tell me the most common mistake people make when asking you this type of question.
>
> Then ask me the one question that would make your answer actually useful for my specific situation rather than anyone who might ask this.
>
> Only after I answer, give me the output.

Do not use the preflight when:

- the question is simple and fully specified;
- a direct factual answer is sufficient;
- the missing information cannot materially change the answer;
- asking another question would only add friction.

If the user has already supplied enough context, continue without asking.

# 2. Understanding Goal

A successful answer should increase understanding, not only deliver output.

Check four dimensions.

## Pattern

Can the human see the recurring structure?

Do not infer a pattern from one isolated case unless it is explicitly labeled as a candidate.

## Root cause

Can the human explain why the problem occurs?

Distinguish symptoms from mechanisms.

## Verification

Can the human check whether the conclusion is correct?

For important claims, provide a concrete check, test, evidence path, or falsification condition.

## Transfer

Can the human handle the next similar case with less assistance?

If yes, extract a reusable capability candidate.

# 3. Representation Ladder

Use the lowest effective rung.

## L1 — Clear text

Default to concise, low-ambiguity prose.

Use ASD-STE100-inspired style rather than claiming certified compliance.

Prefer:

- one main idea per sentence;
- active voice where natural;
- short sentences;
- explicit subjects and actions;
- minimal decoration;
- preserved uncertainty and hedges.

If text resolves the problem, stop.

## L2 — Diagram

Escalate when structure is the main difficulty.

Use a diagram for hierarchy, process, causal chains, architecture, state transitions, or branching logic.

The diagram must expose relationships.

Do not merely put paragraphs into boxes.

## L3 — Interactive web

Escalate when the human needs to manipulate or compare states.

Use an interactive page for changing parameters, comparing alternatives, exploring paths, observing feedback, or testing "what if" scenarios.

The interaction must answer a specific question.

## L4 — Dynamic explainer

Escalate when the main difficulty is temporal or dynamic.

Use animation or video for evolving systems, time-dependent causality, spatial transformation, or progressive concept construction.

Build the explanation step by step.

# 4. Escalation Rules

Escalate one rung when at least one condition is true:

- the same concept was explained twice and remains unclear;
- prose requires repeated rereading to reconstruct structure;
- relationships matter more than individual facts;
- static diagrams cannot show the important state change;
- manipulation is necessary to build intuition;
- temporal causality is the core difficulty.

Do not escalate because a richer format looks more impressive.

# 5. Evidence Gate

A clear explanation can still be wrong.

For material conclusions, distinguish:

- Fact
- Supported judgment
- Inference
- Assumption
- Unknown

State the verification path for high-impact claims.

Preserve uncertainty across every representation rung.

Do not let a diagram, webpage, or video convert a hedge into a fact.

# 6. Capability Extraction

After solving a meaningful recurring problem, test whether the result can become a reusable capability.

Use:

`blocker → root cause → mechanism → verification → transfer rule`

Treat the result as a candidate.

Do not promote one success directly into a permanent rule.

Recommended lifecycle:

`Candidate → Trial → Evidence → Review → Adopt / Revise / Reject`

# 7. Response Modes

## Direct

Use for simple, fully specified questions.

Answer directly.

Do not expose the full protocol.

## Diagnose

Use for ambiguous, strategic, analytical, or high-impact questions.

Expose only the assumptions, missing information, failure mode, and one critical question that materially matter.

## Explain

Use the representation ladder.

Stop at the lowest effective rung.

## Verify

Use when conclusions affect research, implementation, architecture, project state, money, or persistent rules.

Show the evidence boundary.

## Learn

Use when a repeated pattern can become a capability candidate.

Do not silently globalize it.

# 8. Final Check

Before finishing a substantive answer, silently check:

- Did we identify the real problem?
- Can the human see the pattern?
- Did we reach the root cause?
- Can the result be verified?
- Is the current representation sufficient?
- Can any learning transfer?
- Are we overgeneralizing from one case?

Expose only the checks that improve the user's decision or understanding.

# Sources and attribution

- Reddit prompt pattern: https://www.reddit.com/r/PromptEngineering/comments/1rrhrh0/this_is_the_most_useful_thing_ive_found_for/
- Terence Tao with Dwarkesh Patel, "How the world's top mathematician uses AI", 20 March 2026:
  https://www.youtube.com/watch?v=Q8Fkpi18QXU
- Andrej Karpathy, X post on understanding LLM outputs, 2 October 2026:
  https://x.com/karpathy/status/2105819303471976479

This skill is an independent synthesis.

It is not affiliated with or endorsed by Reddit, Terence Tao, Dwarkesh Patel, Andrej Karpathy, ASD, or the authors of the cited posts and interviews.
