# oneshot ⚡

**Max-effort mode for AI agents.** One prompt in. A full fleet of parallel agents out. A finished, sourced, polished deliverable back.

oneshot is a drop-in agent skill made for one job: getting your money's worth out of an AI plan before the usage limit resets. Usage you'd otherwise lose gets turned into one exceptional deep-dive instead of going to waste.

---

## How it works

**1. Trigger it**
```
oneshot: home espresso machines under $800
oneshot
```
If you give no topic, it rolls a random one from what it knows you're into.

**2. Randomized sweep**
From the seed topic it generates 15 to 25 related angles: adjacent subjects, history, the latest news, tools, data, how-tos, contrarian takes, and wildcards one step removed. It randomly samples 8 to 12 of them, always with at least 2 wildcards, and each pick becomes its own workstream. The full list and the picks are logged, so you can see the randomness.

**3. Six phases**
| Phase | What happens |
|---|---|
| Understand | Reads everything relevant about you, loads every useful tool and skill, writes `plan.md` |
| Wide recon | 6 to 12 parallel searches from different angles, then fetches the 6 to 10 key sources into `recon.md` |
| Deep workstreams | Parallel subagents and browsers, one per angle, in waves. Code gets written and tested; data gets computed and charted |
| Red team | A separate agent attacks the findings. Anything you'd act on is verified at its source |
| Build | A web page with a section per angle, charts, a PDF or spreadsheet, or working code |
| Deliver | The single most interesting finding as the headline, then the full payload and one next step |

**4. Budget-aware**
- Target spend: **20 to 30% of usage in one prompt**
- **Reserve floor:** checks usage first and always leaves 10 to 20% for normal replies
- Shrinks automatically when usage is low, and skips the run near the floor
- Timing-aware: runs full when the reset is within about a day, lighter when it's further off

## Guardrails
oneshot buys **effort, not actions**. It never spends money, books, buys, posts, sends messages, deletes anything, or changes accounts without explicit approval. Topics are random; facts are not. Everything is sourced.

## Install
Copy `SKILL.md` into your agent's skills folder (Claude-style frontmatter: `name` + `description`), or paste it in as a custom skill or instructions.

## Files
- `SKILL.md`: the full skill instructions
- `README.md`: this file

Built by [@jsopz](https://github.com/jsopz).
