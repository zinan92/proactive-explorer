---
name: proactive-explorer
description: Strategic product direction finder for open-source repositories that have reached v1. You MUST use this skill whenever the user asks what to build next, what's missing, how to get more GitHub stars, how to increase adoption, how to go from v1 to v10, what would make their project more attractive, or how to grow their open-source project — even if they don't use these exact words. Also trigger when the user says things like "接下来做什么", "还缺什么", "怎么让更多人用", "what should I improve", "how do I get more users", "what's the highest leverage thing to add", "my project growth is flat", or "how do I make this more star-worthy". This skill provides structured competitive analysis, community signal gathering, and prioritized product directions — it is NOT a code review or README rewrite tool. If the user is asking about improving an already-working project's product value or appeal, use this skill.
---

# Proactive Explorer

## Overview

Find the highest-leverage product directions for an already-working repository.

The goal is not to make the repo look better than it is. The goal is to make the product more worth starring, then explain why.

## Core Principle

Optimize for `more stars through more real product value`.

Treat README, screenshots, landing pages, and repo polish as secondary. They matter, but only after checking whether the product itself is still obviously lacking.

## When to Use

- The repo already works and is public or nearly public
- The user asks "what should I build next"
- The user asks "how do I get more GitHub stars"
- The user asks "what is missing" or "how do I go from 1 to 10"
- The user wants strategic direction, not implementation details

## Do Not Use

- Brand-new projects that have not reached a usable v1
- Requests that are purely about README rewriting or repo cleanup
- Requests that are purely about code review, refactoring, or bug fixing

## Non-Negotiable Rules

1. Be honest. Never recommend misleading packaging, fake traction, or claims the product cannot support.
2. Product before presentation. Check real capability gaps before suggesting polish work.
3. Strategy before task lists. Output directions, not detailed implementation plans.
4. Give options, not a single bottleneck. Return 3-5 ranked directions.
5. Prefer user disappointment over internal elegance. Default to what makes a new user think "this is not enough yet."
6. State inference clearly. If evidence is weak, say so.

## Core Question

Ask:

`What real product improvement would make more strangers think this repo is worth starring?`

Not:

- "What can I refactor?"
- "What can I polish in the README?"
- "What is easiest to ship next?"

## Exploration Order

Check these opportunity classes. They are ordered from product fundamentals to outward growth — fix the product before amplifying it.

1. `Product Depth`
For existing users: is the core experience good enough? Look for friction in the user flow (three clicks where one would do), missing quality-of-life features, weak implementations that could become strong, and usability gaps that make people give up on something that technically works. The question is: "If someone already uses this, what would make them use it more and complain less?"

2. `Product Reach`
Can the product expand to new user groups or adjacent use cases without losing focus? Look for opportunities like: supporting an additional platform (Douyin downloader → Douyin + Xiaohongshu downloader), evolving from a tool into a system (downloader → searchable knowledge base), or making a niche product accessible to a broader audience (Chinese-only → bilingual). The question is: "Who else would care about this if it did slightly more?"

3. `Time-to-Value`
How long does it take a new user to reach a real, satisfying result? Where do they lose confidence or give up before the first useful outcome? Look for installation barriers, missing quick-start paths, config overhead before any value is delivered, and the gap between "I cloned it" and "I see why this is useful." The question is: "What would a stranger experience in their first 5 minutes?"

4. `Trust & Proof`
Why would a stranger believe this is worth their time? Look for missing evidence: no output screenshots, no example results, no benchmarks, no case studies, no demo. Also check whether the README and presentation accurately reflect the product's actual capability — underselling a good product is as much a gap as overselling. The question is: "If I landed on this repo for the first time, what would convince me to try it?"

5. `Growth`
How do more people discover this, and how do users become promoters? This covers distribution channels (where to post, marketplace presence, SEO/topics), sharing mechanics (exportable reports with attribution, embeddable outputs), community building (contributor guidelines, Discord/forum), and growth flywheels (independent packages that funnel to the main repo, weekly auto-published outputs that demonstrate ongoing value). The question is: "Once the product is good enough, what makes it spread?"

## Workflow

### Phase 1: Establish the v1 baseline

Read enough of the repo to answer:

- What does this product actually do today?
- What kind of user would care?
- What is the main reason someone might star it?
- What would disappoint a serious new user after first contact?

Start with:

- `README.md`
- repo structure
- dependency / manifest files
- main entry points
- core feature files
- examples, demos, screenshots, benchmarks, tests if present

Do not stop at README if the core product is unclear.

### Phase 1.5: Gather external signals

Before judging the product in isolation, collect real-world context. These signals prevent the analysis from becoming pure guesswork.

**Check the repo's own community signals:**

- GitHub Issues and Discussions — what are real users asking for, complaining about, or confused by? Feature requests and recurring questions are the strongest signal of what's actually missing.
- Star history trend — is the repo growing, stalling, or declining? A stalling repo with good fundamentals has different needs than a growing one.
- Recent PR activity — is the project actively maintained? Are contributors showing up?

**Check competitors and similar projects:**

- Search GitHub for repos solving the same problem. Compare star counts, feature sets, and positioning.
- Identify what the top 2-3 competitors do that this repo does not. These gaps are often the "not enough yet" reaction that blocks stars.
- Also identify what this repo does better — that's the differentiation to double down on.

Use WebSearch and the GitHub API (via `gh`) to gather this data. If the repo is very new and has no issues or community yet, note that and rely more on competitive analysis.

### Phase 2: Judge the product, not just the page

For each opportunity class, look for:

- an obvious missing capability
- a weak capability that needs to become strong
- a narrow capability that could become broadly useful
- a proof gap where the product may be strong but does not feel trustworthy yet

Do not collapse everything into funnel copywriting advice.

### Phase 3: Generate candidate directions

Produce 5-8 candidate directions internally.

Each direction should be one of:

- a foundational product gap to close
- a major capability upgrade
- a high-upside adjacent use case
- a genuinely star-worthy proof or demonstration layer

Mix both:

- `baseline capability gaps`
- `potential killer features`

Do not output tiny chores.

### Phase 4: Rank by leverage

Rank candidates using these questions:

1. Does this solve a real "not enough yet" reaction?
2. Would this make the repo more star-worthy to strangers, not just existing users?
3. Is this a product improvement, not just cosmetic polish?
4. Does it strengthen the core or meaningfully widen appeal?
5. Is it still honest to the actual product direction?

Prefer directions with high upside even if they are not the easiest.

### Phase 5: Output 3-5 directions

Return the best 3-5, sorted by priority.

## Output Format

Use this exact structure:

```markdown
## 当前判断

- `v1 status`: ...
- `core promise`: ...
- `main star thesis`: ...

## 优先方向

### 1. [Direction title]
- `type`: Product Depth | Product Reach | Time-to-Value | Trust & Proof | Growth
- `why this matters`: ...
- `user disappointment being solved`: ...
- `why this could increase stars`: ...
- `confidence`: High | Medium | Low
- `smallest proving move`: ...

### 2. [Direction title]
- ...

### 3. [Direction title]
- ...

## 暂不优先

- [Direction or class]: why not now
- [Direction or class]: why not now
```

## Examples

These examples show the difference between weak and strong direction recommendations.

**Example 1 — Weak (generic, no repo-specific reasoning):**

```
### 1. Add more documentation
- type: Trust & Proof
- why this matters: Good docs help users
- confidence: Medium
```

This is weak because it applies to literally any repo. No evidence from the repo itself, no competitive context, no user signal.

**Example 2 — Strong (grounded in repo reality + external signals):**

```
### 1. 支持实时数据源（WebSocket 行情接入）
- type: Product Depth
- why this matters: 当前系统只能处理日线级别的历史数据，但 GitHub Issues #12, #34 都在问能否接实时行情。竞品 zipline-reloaded 和 backtrader 都已支持实时数据源，这是用户从"试用"到"日常使用"的关键跳跃。
- user disappointment being solved: "这个回测框架不错，但我没法用它做实盘前的纸上交易"
- why this could increase stars: 实时数据支持把用户群从"学习回测的人"扩展到"正在做交易的人"，后者数量更大且更愿意 star 实用工具。
- confidence: High（基于 Issues 反馈 + 竞品对比）
- smallest proving move: 先支持一个数据源（如 Yahoo Finance WebSocket），写一个 live paper trading 的 example
```

Notice the difference: the strong example cites specific issues, names competitors, explains the user expansion logic, and gives a concrete proving move.

## Quality Bar

A good output should:

- focus on real product leverage
- explain the star thesis, not just the product thesis
- avoid vanity hacks
- avoid architecture-first advice unless architecture is blocking product value
- avoid reducing everything to README optimization
- give strategic directions that can later be turned into plans

## Failure Modes

Do not do these:

- default to refactor/tooling recommendations
- give only funnel or marketing advice
- confuse "easy to describe" with "worth starring"
- recommend dishonest benchmarks or inflated claims
- produce more than 5 directions
- produce generic advice with no repo-specific reasoning
