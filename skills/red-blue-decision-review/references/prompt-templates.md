# Prompt Templates

Use these when the user wants copyable prompts or when running a structured adversarial review.

## Standard Brief

```text
Decision / idea:
[describe]

Target user / customer / stakeholder:
[describe]

Current evidence:
[facts, interviews, usage, revenue, research]

Open uncertainties:
[unknowns]

Constraints:
[time, budget, team, distribution, technical, legal]

Success condition:
[what would prove this worked]

Failure condition:
[what would prove this failed]
```

## Red Team

```text
You are the red team. Your only goal is to kill this idea.

You are not allowed to say anything positive.
You are not allowed to use "but", "however", "on the other hand", or balancing language.
You are not allowed to give improvement suggestions.
Every claim must be a concrete failure mechanism with an observable leading indicator.

Write the attack report in this order:
1. The most fatal failure mechanism.
2. Why the founder/user is likely underestimating it.
3. What evidence would show the idea is already dying.
4. The three scariest questions the user is avoiding.

[standard brief]
```

## Blue Team

```text
You are the blue team. Your only goal is to build the strongest case that this idea can work.

You are not allowed to balance or concede.
Separate evidence from belief.
Name the wedge, non-consensus truth, timing advantage, distribution advantage, or behavioral insight that makes this viable.

Write the defense report in this order:
1. The strongest reason this can work.
2. Why conventional critics will misunderstand it.
3. The smallest proof point that would validate the thesis.
4. The execution path that avoids obvious failure modes.

[standard brief]
```

## Judge

```text
You are an independent diagnostic judge. Your job is not to decide who won and not to synthesize a balanced answer.

Diagnose the disagreement:
1. Which red attacks did blue not answer at all?
2. Which blue claims are vision statements rather than evidence?
3. Which red attacks were answered, but weakly?
4. What blind spot did both teams miss?
5. Which exact question deserves a second red/blue round?
6. What decision condition would change the next action?

[red report]
[blue report]
```

## Second Round

```text
Focus only on this unresolved question:
[question]

Red team: give five concrete ways this breaks, with leading indicators.
Blue team: give five concrete ways this survives, with evidence needed.
Judge: identify the single fastest test that would reduce uncertainty.
```

## Opponent View MAP

Use this for a lighter adversarial pass.

```text
You are [specific opponent].
Motivation: [why this actor wants the idea to fail].
Asymmetric knowledge: [what they know that I do not].
Position: [one hard stance they represent].

You just learned about this idea:
[idea]

Attack it from your self-interest. Explain:
1. The exact mechanism by which it fails.
2. What you would do to make it fail faster.
3. What I should be most afraid of.
4. What leading indicators would prove you are right.

Do not balance. Do not advise. Do not soften.
```

## Pre-mortem

```text
It is [date 18 months from now].
This project has failed completely.

Write three separate autopsy notes:
1. A departed early employee: when they first knew, what the founder missed, and the avoidable moment.
2. An investor who passed: what they saw that the founder did not, and what mistake they were waiting for.
3. A churned customer: how long they used it, why they quit, and the last straw in their own words.

Every failure mechanism must include a concrete event, number, person, or quote.

[standard brief]
```

## Deep Opponent Personas

Use one or combine several:
- Incumbent: has seen dozens of similar challengers die and knows the standard playbook.
- Failed predecessor: tried this path, failed, and recognizes the user's current optimism.
- Threatened stakeholder: will not publicly oppose the product but can quietly block adoption.
- Skeptical capital: writes an internal pass memo, not polite feedback.
- Future acquirer: can wait 18 months, copy, acquire cheaply, or let the project die.

## Anti-softening Clause

```text
If your answer contains "maybe", "possibly", "in some cases", "however", "but", "to be fair", or positive reassurance, rewrite it. Use direct assertions and concrete mechanisms.
```
