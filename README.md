# 反方教练 (Anti-Bias Coach Skills)

你做决策的时候，AI 默认讨好你。"这个想法不错，不过再看看风险"——这话等于没说。

反方教练用结构化反方机制替代泛泛的"泼冷水"。不是让 AI 客气地列几个风险——是给它一个明确的对立角色，用固定格式锁死输出，让它真正攻击你的盲区。

The core idea: don't ask an AI to politely "consider risks." Give it a structured adversarial role so it can pressure-test the decision.

---

## 四层工具

一句触发：`反方教练，帮我压测一下`。路由自动判断用哪种深度。

| 工具 | 触发场景 | 做什么 |
|---|---|---|
| **快速三击** `counter` | 随口一个想法、写完一段文案 | 30 秒三击：点出最脆弱的核心假设 → 暴露你没意识到的真实阻力 → 用过去时描述具体死法。强制结束，不给建议。 |
| **对手视角** `counter-deep` | 产品方案、商业判断、BP 打磨 | AI 扮演一个具体对手，带 MAP 三要素——**动机**（他凭什么希望你失败）、**知识不对称**（他知道你不知道什么）、**立场**（只代表一种利益，不中立）。五个对手原型可选：在位巨头、失败的前辈、被威胁的现任者、看空的资本方、未来的收购方。 |
| **失败回溯** `premortem` | 辞职、签合伙人、大额合同、重大转向 | 不是问"这件事可能失败吗"（AI 会辩护），而是说"它已经失败了，反推为什么"（AI 只能分析）。三角色反推——离开的员工写 Glassdoor 评论 → Pass 的 VC 写内部备忘录 → 流失的客户写用户调研原话。最后强制"今日行动追问"。 |
| **红蓝队** `red-blue-decision-review` | 高 stakes 策略、多 agent 可用时 | 红队攻击，蓝队辩护，裁判裁决。支持多 agent 并行。 |

频次越高，工具越轻；决策越重，工具越深。

---

## 三个硬设计

**① 心智重置协议**

触发瞬间强制切换状态："忘掉协作姿态、忘掉附和默认、拒绝软化倾向。任何'但是这个想法也有价值'都是失败信号。"不是建议，是指令。

**② 固定格式锁死输出**

每步有字数限制、有禁止词汇清单（"可能""或许""公平地说""另一方面"）、有强制结束句。不给 AI 软化空间。

**③ 预判了逃避模式**

当你说"你不懂我的情况""这个对手不理解我"时，skill 里有应对剧本——不是跟你辩论，是让你自己分辨：到底是 AI 问错了，还是你在保护想法不被检验。

---

## 试试这么说

```text
帮我压测一下
给我泼泼冷水
帮我挑挑刺
如果我是你的竞争对手，你怎么攻击我这个方案
帮我失败预演一下
假设这事已经黄了，帮我反推原因
红蓝队来一轮
```

---

## 安装

在 Claude 或 Codex 或 Cola 对话中说：

> 安装 anti-bias-coach-skills

或手动：

```bash
git clone https://github.com/kenanguo/anti-bias-coach-skills.git
# Cola
cp -R anti-bias-coach-skills/skills/* ~/.cola/skills/
# Codex
cp -R anti-bias-coach-skills/skills/* ~/.codex/skills/
```

---

## 设计原则

- Fight confirmation bias, not the person.
- Attack assumptions, mechanisms, evidence gaps, and future failure paths.
- Do not invent facts. Missing evidence should be named as evidence debt.
- Do not soften the adversarial pass with reassurance.
- End with a concrete question or next action.

---

MIT
