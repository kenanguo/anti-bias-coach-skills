# Anti-Bias Coach Skills

反方教练是一组用于对抗确认偏误的 Agent Skills。它把一个想法、决策、产品方向或创业判断放进反方机制里，帮助你更早看到脆弱假设、真实阻力和失败路径。

The core idea: do not ask an AI to politely "consider risks". Give it a structured adversarial role so it can pressure-test the decision.

## What's Included

This repository contains one router skill and four method skills:

| Human name | Skill folder | Use when |
|---|---|---|
| 反方教练 | `anti-bias-coach` | You want one easy entry point and want the agent to choose the right mode |
| 反方教练：快速三击 | `counter` | You want a quick, sharp challenge to an idea or claim |
| 反方教练：对手视角 | `counter-deep` | You want a concrete opposing persona, such as an incumbent, failed predecessor, skeptical investor, or future acquirer |
| 反方教练：失败预演 | `premortem` | You want to rehearse how a major decision could fail before committing |
| 反方教练：红蓝队 | `red-blue-decision-review` | You want a heavier red team / blue team / judge process, including multi-agent use when available |

## Example Prompts

```text
反方教练，帮我压测这个想法
反方教练，快速反方一下
反方教练，用对手视角深挖
反方教练，失败预演一下
反方教练，提前复盘一下
反方教练，红蓝队对抗
```

English prompts also work:

```text
Use anti-bias coach to pressure-test this strategy.
Run a quick counter on this claim.
Use an incumbent competitor persona to attack this product idea.
Run a failure rehearsal before I commit.
Run a red team / blue team review.
```

## Installation

For Codex, copy the skill folders into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -R skills/* ~/.codex/skills/
```

Restart Codex so the new skills are picked up.

## How To Choose a Mode

Use the router first:

```text
反方教练，帮我压测一下
```

The router will choose the lightest method that can change the next action:

- Low-stakes or casual idea: quick counter.
- Concrete product or business plan: opponent view.
- Irreversible commitment: failure rehearsal.
- High-stakes strategy or explicit multi-agent request: red/blue review.

## Design Principles

- Fight confirmation bias, not the person.
- Attack assumptions, mechanisms, evidence gaps, and future failure paths.
- Do not invent facts. Missing evidence should be named as evidence debt.
- Do not soften the adversarial pass with reassurance.
- End with a concrete question, evidence need, or next test.

## License

MIT
