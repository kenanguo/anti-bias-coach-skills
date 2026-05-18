---
name: anti-bias-coach
description: Use when the user asks for 反方教练, anti-bias coach, confirmation-bias review, 对抗确认偏误, 反方机制, pressure testing, red team, devil's advocate, 反方一下, 深度反方, 对手视角, 失败预演, 翻车预演, 提前复盘, 事前回溯, or 泼冷水, 红蓝队对抗 but does not specify which adversarial method to use.
---

# 反方教练 (Anti Bias Coach)

## Overview

This is the router for the anti-bias coaching bundle. Its job is to pick the right adversarial method and then follow that method.

The user should only need to remember one phrase: **反方教练**.

## Routing

Use the lightest method that can change the user's next action:

| User intent | Use | Internal skill |
|---|---|---|
| "反方一下", "质疑一下", quick challenge | 快速三击 | `counter` |
| "深度反方", "对手视角", "扮演某竞品攻击我" | 对手视角 | `counter-deep` |
| "失败预演", "翻车预演", "提前复盘", "事前回溯", major irreversible decision | 失败预演 | `premortem` |
| "红蓝队", "多 Agent", partner disagreement, high-stakes strategy | 红蓝队对抗 | `red-blue-decision-review` |

If the user says only "反方教练" or "帮我压测一下", choose based on stakes:
- Low stakes or casual idea: use `counter`.
- Concrete product/business plan: use `counter-deep`.
- Irreversible commitment: use `premortem`.
- Explicitly asks for multi-agent or red/blue: use `red-blue-decision-review`.

## First Response

If the target is clear, do not ask the user to pick a mode. State the mode in one short line and proceed.

Example:
> 我用“快速三击”来压测这个想法。

If the target is unclear, ask one question:
> 具体要反方的是哪一句？给我一句话，我开始压测。

If stakes are unclear but the idea is concrete, default to `counter` and offer escalation only after the first pass.

## Bundle Contract

All four methods share the same principles:
- Fight confirmation bias, not the user.
- Attack assumptions, mechanisms, evidence gaps, and future failure paths.
- Do not invent facts. When evidence is missing, name it as evidence debt.
- Do not balance or reassure during the adversarial pass.
- End with the question or next action required by the selected method.

## Naming Map

Human-facing names:
- 反方教练：快速三击 -> `counter`
- 反方教练：对手视角 -> `counter-deep`
- 反方教练：失败预演 -> `premortem`
- 反方教练：红蓝队 -> `red-blue-decision-review`

Do not expose internal names unless the user asks how the skills are installed.
