# Understand First

**Diagnose before answering. Optimize for understanding. Escalate the representation only when needed. Verify before turning an answer into a rule.**

`understand-first` is a Human–AI problem-solving skill for questions where a good answer is not enough.

It is designed for work where the human must understand **what is happening, why it is happening, how to check it, and what can be reused next time**.

## Why this skill exists

As AI produces more of the first-pass work, the bottleneck moves toward human judgment.

A model can generate a plausible answer quickly.

That does not guarantee that:

- the question was framed correctly;
- hidden assumptions were exposed;
- the root cause was found;
- the result was verified;
- the learning can transfer to another project.

`understand-first` adds a lightweight control loop around the answer.

```text
Question
  ↓
Preflight diagnosis
  ↓
Answer / reasoning
  ↓
Lowest effective representation
  ↓
Evidence gate
  ↓
Capability candidate
```

## The three source ideas

This skill is a synthesis of three independent sources.

### 1. Reddit: diagnose before committing

A widely shared Reddit prompt asks the model to identify:

1. unstated assumptions;
2. missing information that could change the answer;
3. the most common mistake for this class of problem;
4. one critical question before producing the final answer.

In this skill, that preflight block is **canonical**.

It should not be casually rewritten or expanded.

Its job is not to make every answer longer.

Its job is to stop the model from confidently answering the wrong problem.

### 2. Terence Tao: correct output is not the same as understanding

In his March 2026 conversation with Dwarkesh Patel, Terence Tao discusses a central problem created by stronger AI systems: producing or verifying an answer does not automatically give humans understanding.

Humans still need to evaluate results, connect ideas, explain them, and decide what matters.

This skill turns that principle into four operational goals:

```text
Pattern
  ↓
Root cause
  ↓
Verification
  ↓
Transfer
```

This four-part formulation is our synthesis, not a direct quotation from Tao.

### 3. Andrej Karpathy: change the representation when text is the bottleneck

On 2 October 2026, Andrej Karpathy proposed a ladder for understanding model output:

```text
STE-style writing
  ↓
Diagram
  ↓
Interactive web page
  ↓
Explainer video
```

`understand-first` uses this as a **representation escalation ladder**.

It does not generate all four formats by default.

It starts at the cheapest rung and climbs only when the current format is the reason understanding is blocked.

## Operating principle

Use the smallest intervention that changes the quality of understanding.

- Simple question → answer directly.
- Ambiguous or strategic question → run the canonical preflight.
- Structural confusion → use a diagram.
- State or parameter confusion → use an interactive model.
- Dynamic or temporal confusion → use a progressive explainer.
- High-impact conclusion → run the evidence gate.
- Repeated successful mechanism → extract a capability candidate.

## Understanding test

A response is successful when the human can answer four questions:

1. **Pattern** — What repeats?
2. **Root cause** — Why does it happen?
3. **Verification** — How can I check this?
4. **Transfer** — What can I do next time without starting from zero?

If these four questions cannot be answered, a polished output may still be a weak explanation.

## Evidence boundary

Better presentation does not make weak evidence stronger.

The skill distinguishes fact, supported judgment, inference, assumption, and unknown.

Uncertainty must survive the climb from text to diagram to web page to video.

## Capability lifecycle

One successful answer does not become a global rule.

Reusable learning should move through:

```text
Candidate
  ↓
Trial
  ↓
Evidence
  ↓
Review
  ↓
Adopt / Revise / Reject
```

## Recommended use cases

Use `understand-first` for architecture decisions, research design, root-cause analysis, project blockers, repeated debugging, complex reading, workflow redesign, evidence review, and decisions that may become reusable rules.

Do not force it onto trivial factual questions.

## Installation

```text
skills/
└── understand-first/
    ├── SKILL.md
    ├── README.md
    └── README.zh-CN.md
```

Point your agent or coding environment to `SKILL.md`.

## Suggested invocation

```text
Use understand-first on this problem.
```

or:

```text
先理解，不要急着回答。用 understand-first 分析这个问题。
```

The full preflight should run only when it can materially improve the answer.

## Sources

- Reddit prompt pattern:
  https://www.reddit.com/r/PromptEngineering/comments/1rrhrh0/this_is_the_most_useful_thing_ive_found_for/
- Terence Tao with Dwarkesh Patel, *How the world's top mathematician uses AI*, 20 March 2026:
  https://www.youtube.com/watch?v=Q8Fkpi18QXU
- Andrej Karpathy, post on understanding LLM outputs, 2 October 2026:
  https://x.com/karpathy/status/2105819303471976479

## Attribution note

`understand-first` is an independent synthesis.

The Reddit preflight, Tao's discussion of human understanding, and Karpathy's representation ladder are separate source ideas.

The combined workflow, evidence gate, and capability-transfer lifecycle are the design of this skill.

The project is not affiliated with or endorsed by the cited authors or platforms.
