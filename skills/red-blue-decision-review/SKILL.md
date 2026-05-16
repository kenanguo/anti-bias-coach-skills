---
name: red-blue-decision-review
description: Use when the user asks for 反方教练 red-blue mode, 红蓝队对抗, automatic multi-agent adversarial review, stress-testing important decisions, startup or product ideas, strategy, assumptions, confirmation bias, red-team or blue-team debate, adversarial review, opposing views before committing, or Chinese requests like 反方辩论, 对抗确认偏误, 反方 prompt.
---

# Red Blue Decision Review

## Overview

Use this skill to turn an important decision into an adversarial collaboration: isolated red team, isolated blue team, independent diagnosis, then a second round on the hardest unresolved points.

The goal is not to get the model to decide for the user. The goal is to upgrade the question quality from "should I do this?" to "under what concrete conditions would this survive?"

## When to Use

Use for:
- Irreversible or expensive decisions: hiring, pivoting, fundraising, product direction, market entry, major build choices.
- Startup, product, strategy, writing, investment, or career ideas where confirmation bias is likely.
- User asks for red team, blue team, devil's advocate, pre-mortem, opposing view, adversarial review, or "challenge this".
- User asks in Chinese for 红蓝队对抗, 反方辩论, 对抗确认偏误, 事前验尸, 反方 prompt, or 让 AI 当反方.
- User asks for automatic multi-agent analysis of a decision.

Do not use for routine small choices, already-decided self-justification, or when the user only needs a factual answer.

## First Move

Ask for missing essentials only if they are required:
- Decision or idea being tested.
- Current evidence.
- Stakes, timeline, and what would make the decision reversible or irreversible.

If enough context exists, proceed. Do not wait for perfect information.

## Choose Depth

Pick the lightest mode that can change the decision:

| Situation | Mode |
|---|---|
| Early idea, low cost | Opponent View |
| Strategy pressure test | Short Seller |
| Final check before commitment | Pre-mortem |
| High stakes, partner disagreement, irreversible move | Full Red/Blue |

For Full Red/Blue, use actual subagents or separate model sessions when the user explicitly asked for multi-agent work and the platform allows it. Otherwise, run isolated passes in one response and clearly label them as simulated, not truly isolated.

## Full Red/Blue Protocol

### 1. Standardize the Brief

Create a neutral brief before any team argues. Include only the information both teams should see:
- Decision or idea.
- Target user/customer/stakeholder.
- Current evidence and uncertainties.
- Constraints: budget, time, team, distribution, legal or technical limits.
- What success and failure would look like.

Red team and blue team must receive the exact same brief.

### 2. Red Team

Red team has one job: kill the idea.

Rules:
- No positive statements.
- No "but", "however", "on the other hand", or balancing language.
- No vague hedging such as "maybe", "possibly", "in some cases".
- Every claim should include a concrete failure mechanism and an observable leading indicator.

When picking a red persona, prefer MAP:
- Motivation: why this actor wants the idea to fail.
- Asymmetric knowledge: what they know that the user does not.
- Position: the single hard stance they represent.

Strong red personas: incumbent, failed predecessor, threatened internal stakeholder, skeptical capital provider, future acquirer, short seller.

### 3. Blue Team

Blue team has one job: build the strongest case that the idea can work.

Rules:
- No balancing or concessions.
- Separate evidence from belief.
- Name the non-consensus truth, unfair advantage, or wedge that could make the idea survive.
- Answer how the plan beats each obvious failure path without seeing red team's report.

### 4. Judge

Judge diagnoses, not averages. Do not ask "who is right?" Ask:
- Which red attacks did blue not answer at all?
- Which blue claims are vision statements rather than evidence?
- Which attacks were answered weakly? Quote or cite both sides.
- What blind spots did both sides miss?
- Which one or two questions deserve a second round?
- What decision conditions would change the recommendation?

### 5. Second Round

Run another red/blue pass only on the highest-leverage unresolved question. The second round should be narrow, concrete, and evidence-seeking.

## Output Format

Return:
1. Decision diagnosis: the live question that matters most.
2. Strongest red attacks: concrete failure mechanisms and leading indicators.
3. Strongest blue defenses: evidence, wedge, or asymmetric advantage.
4. Evidence debt: what must be verified before committing.
5. Second-round target: the one question to attack again.
6. Actionable next tests: 3-5 checks the user can run now.

Avoid generic advice. If the output would not change the next action, keep pushing for sharper indicators.

## Prompt Templates

For reusable prompt blocks and specialized variants, read [references/prompt-templates.md](references/prompt-templates.md).

## Common Mistakes

- Running red and blue in the same context and calling it isolated.
- Asking the judge to synthesize a balanced answer.
- Letting red team give suggestions.
- Letting blue team see red team's attack.
- Accepting abstract risks like "market", "execution", or "competition" without concrete events, people, numbers, and dates.
- Stopping after the first round instead of drilling into the one unresolved point that actually matters.
