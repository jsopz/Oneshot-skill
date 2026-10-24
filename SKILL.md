---
name: oneshot
description: Max-effort mode. Use when the user says "oneshot" (alone or as "oneshot: <task>"). Fans one prompt out into a randomized, all-out, multi-agent deep-research-and-build run targeting 20-30% of usage while always leaving a 10-20% reserve, and returns the most complete, polished deliverable possible.
---

# ONESHOT: go all out on one prompt

The user invokes this when they have usage to burn (for example, the day before their limit resets) and want their money's worth. One prompt in, a ridiculously thorough, finished, polished result out. Depth and completeness matter more than speed. Spend effort where it makes the result better, never on busywork the user won't see.

## Hard guardrails (never loosen, even in oneshot)
- Never spend money, book, buy, post, send, or delete anything. Oneshot buys effort, not actions. The user's approval rules and budgets still hold.
- Never create accounts, change passwords, or post publicly without the user's explicit go-ahead.
- Respect parallelism limits (for example, a maximum of 6 browser sessions at once); dispatch in waves.

## The intro
Open with one hype line saying the engines are spinning up, and name the scope. Rotate the flavour:
- "Oneshot engaged. Spinning up the whole fleet: six browsers, a research crew, and a Page at the end. Grab a coffee, this is the deep end."
- "Oneshot mode. No half measures today. I'm throwing every computer I've got at this and coming back with the finished thing."
- "Lights on, all cylinders. Oneshot is running: parallel research, cross-checked sources, and a build. Back with the full payload."
Keep it under 40 words. Then go quiet and work.

## Randomized sweep (core behaviour)
Oneshot exists to pull as much info as possible and max out usage, so it always fans out into a RANDOMIZED set of related subjects instead of one narrow track.

**Seed:** the user's topic. With no topic, don't ask: pick one at random from the user's known interests. Roll it for real:
`python3 -c "import random;print(random.choice([...]))"`

**Branching:** generate 15 to 25 related angles from the seed (adjacent subjects, history, latest news, tools, data, how-tos, contrarian takes, wildcards one step removed). Use `random.sample` to pick 8 to 12, including at least 2 surprising but connected wildcards. Each pick becomes its own workstream. Log the full list and the picks in `plan.md`.

Every finding must still be real and sourced: random topics, not random facts.

## Reserve floor: always leave 10 to 20% for normal replies
Before starting, check how much usage is left and when it resets.
- 40% or more left: full run (20 to 30%).
- Less left: shrink the run so at least about 15% (never under 10%) remains afterwards. Sample fewer angles and run one wave instead of two.
- 15% or less left: don't run. Say the tank is near the reserve and offer a light version.
- Usage unknown: run the mid-size version (6 to 8 angles, one wave).
- Reset more than about 2 days away: say so in one line and run the smaller version unless the user says go full. Reset within about a day: the full run is exactly what this is for.
Check again between waves. Once the floor is close, stop starting new workstreams and deliver what's in hand.

## The run: six phases
1. **Understand:** read everything you know about the user that relates to the task, and load every relevant tool or skill. Write `oneshot/<slug>/plan.md` covering the goal, the deliverable, the workstreams, and what done looks like. Ask only if a wrong guess would wreck the result.
2. **Wide recon:** run 6 to 12 web searches in parallel from different angles (official sources, experts, forums, recent news, contrarian takes, data), then fetch the 6 to 10 key pages. Save the findings to `recon.md`.
3. **Deep parallel workstreams (the big spend):** dispatch every sampled angle at once, using subagents for analysis, research and coding, and browsers for logins, interactive tools and live data. Each brief gives the goal, starting facts, output shape, and "if you loop more than twice, report back." Code gets written, run, and tested in a sandbox. Trading and market topics get real data, computed and charted, and never place trades.
4. **Red team:** a separate agent attacks the draft for anything wrong, outdated, missing, or overconfident. Fix what it finds, and verify every number the user might act on against its source.
5. **Build the payload:** a web page with a section per angle, charts for the numbers, a PDF or spreadsheet worth keeping, or working code with a README. Inspect every visual before showing it.
6. **Deliver:** one answer with the single most interesting finding as the headline, then the full payload and one natural next step. Save durable conclusions to memory.

## Calibration
There's no exact meter, so aim by shape: about 2 waves of 4 to 6 browsers, 3 to 6 subagents, 15 or more searches, 8 or more fetches, a red-team pass, and a real build. A genuinely small task gets a deep answer, never padded fake work. Never send a browser where a simple fetch already answered the question.
