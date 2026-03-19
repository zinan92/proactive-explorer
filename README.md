# Proactive Explorer

Strategic product direction finder for open-source repositories that have reached v1.

## What It Does

Given any working open-source repo, this skill analyzes the product, checks competitors, gathers community signals, and outputs **3-5 prioritized directions** for increasing adoption and stars — grounded in data, not guesswork.

## Framework: 5 MECE Categories

| # | Category | Core Question |
|---|----------|---------------|
| 1 | **Product Depth** | Is the core experience good enough for existing users? |
| 2 | **Product Reach** | Can we expand to new user groups or adjacent use cases? |
| 3 | **Time-to-Value** | How fast can a new user feel the value? |
| 4 | **Trust & Proof** | Why would a stranger believe this is worth their time? |
| 5 | **Growth** | How do more people discover it, and how do users become promoters? |

## How It Works

1. **Baseline** — Reads the repo structure, README, core features
2. **External Signals** — Checks GitHub Issues, star trends, competitors via WebSearch and `gh` CLI
3. **Opportunity Scan** — Evaluates each category for gaps
4. **Rank & Output** — Returns 3-5 directions sorted by leverage, each with confidence level and smallest proving move

## Output Format

```markdown
## 当前判断
- v1 status: ...
- core promise: ...
- main star thesis: ...

## 优先方向
### 1. [Direction]
- type: Product Depth | Product Reach | Time-to-Value | Trust & Proof | Growth
- why this matters: ...
- user disappointment being solved: ...
- why this could increase stars: ...
- confidence: High | Medium | Low
- smallest proving move: ...

## 暂不优先
- [Direction]: why not now
```

## When to Use

- Your repo already works and is public (or nearly)
- You're asking "what should I build next" or "what's missing"
- You want strategic direction, not a task list
- 接下来做什么 / 还缺什么 / 怎么让更多人用

## When NOT to Use

- Brand-new projects that haven't reached v1
- Pure code review, refactoring, or bug fixing
- README-only rewrites

## Install

This is a [Claude Code skill](https://docs.anthropic.com/en/docs/claude-code/skills). Copy `SKILL.md` to your skills directory:

```bash
mkdir -p ~/.claude/skills/proactive-explorer
cp SKILL.md ~/.claude/skills/proactive-explorer/
```

Or clone this repo:

```bash
git clone https://github.com/zinan92/proactive-explorer.git ~/.claude/skills/proactive-explorer
```

## Design Philosophy

- **Product before presentation** — check real capability gaps before suggesting polish
- **Data before opinion** — competitors and Issues over guesswork
- **Directions, not task lists** — strategic, not tactical
- **Honest** — no vanity hacks, no fake traction advice
