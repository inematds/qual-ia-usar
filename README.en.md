# ⚖️ Which AI to Use

**🇧🇷 [Português](README.md) · 🇺🇸 [English](README.en.md) · 🇪🇸 [Español](README.es.md)**

[![Which AI Is Cheaper](guia/assets/banner-en.jpg)](https://inematds.github.io/qual-ia-usar/guia/en/)

## What It Is

This project compares ten AI models from three companies: Google’s Gemini 4 (Neon, Argon, and Hydrogen), Anthropic’s Claude (Fable, Opus, Sonnet, and Haiku), and the OpenAI models used by Codex (Astra, Sol, and Luna). It combines official pricing tables with the Agent Arena leaderboard, a public ranking that measures AI agents performing real tasks, accessed on 11/19/2026. It’s for people who pay for AI and want to choose without wasting money. You don’t need anything to read it; to test a model with your own task, you just need Claude Code or Codex.

## 📖 Guide

Complete guide in plain language: **https://inematds.github.io/qual-ia-usar/guia/en/**

## The Idea in One Line

The cheapest AI in the pricing table can end up costing more on your bill. What matters is the **cost per successful delivery**: everything you paid, including failed attempts, divided by the tasks that were completed successfully.

## Who Wins in Each Tier (11/19/2026)

Price in US$ per million tokens (input / output). Score and cost per task: Agent Arena.

| Tier | Google | Anthropic | OpenAI |
|---|---|---|---|
| Complex work | Gemini 4 Neon · 3 / 15 · score 1333 · US$ 2,60 per task | Claude Opus 5.5 · 4 / 20 · 1336 · US$ 5,98 | GPT-6.2 Astra · 8 / 40 · 1291 · US$ 3,11 |
| Everyday use | Gemini 4 Argon · 2 / 10 (4 / 20 starting Dec. 1) · 1229 · US$ 0,66 | Claude Sonnet 5.5 · 2 / 10 · 1296 · US$ 3,27 | GPT-6.2 Sol · 2 / 10 · 1241 · US$ 0,96 |
| High volume | Gemini 4 Hydrogen · 1,50 / 7,50 · 1271 (preliminary) · US$ 1,50 | Claude Haiku 5.5 · 0,10 / 0,50 · no score | GPT-6 Luna · 0,10 / 0,50 · no score |

Outside these tiers: **Claude Fable 5.2** (US$ 8 / 40) leads the leaderboard with a score of 1448 and costs US$ 9,16 per task.

- **Complex work:** Neon nearly ties with Opus and costs less than half as much per task.
- **Everyday use:** all three charge the same per token; per task, Argon is cheaper and Sonnet has the highest score.
- **Volume:** Haiku and Luna charge 15 times less per token than Hydrogen; their quality can only be determined by testing.
- **Within Google:** Hydrogen is cheaper per token than Argon, but cost more than twice as much per task.

What this comparison does not promise: these are published figures (no tests of our own with all ten models yet), the leaderboard measures agents doing tasks in general, not your tasks, and everything changes over time.

## How to Get Started (Without Programming)

Open Claude Code or Codex in one of your folders and paste:

```text
Read the "Qual IA usar" project at https://github.com/inematds/qual-ia-usar (the README explains the method and calculator).
I want to know which AI costs less per successful delivery for one of my tasks: [describe the task and what counts as "successful"].
1. Tell me, in plain English, which 3 or 4 models are worth testing for this task and why.
2. Propose a small test: how many times to run each model and how much it should cost.
3. Don't call any model or spend anything before I say yes.
After I say yes, record each attempt in the project's format, run the calculator, and show me the result.
```

---

## Technical Installation

All you need is Python 3 (no extra libraries).

```bash
git clone https://github.com/inematds/qual-ia-usar
cd qual-ia-usar
python3 calcular.py --precos                              # table of prices per token
python3 calcular.py --arena                               # Agent Arena leaderboard + points per dollar
python3 calcular.py exemplos/tentativas-exemplo.csv       # fictional test example
```

### Files

| File | What It Is |
|---|---|
| `calcular.py` | Calculates the cost per successful delivery from a CSV of attempts |
| `dados/precos-2026-11-19.csv` | Official prices per million tokens, with the source for each row |
| `dados/arena-2026-11-19.csv` | Agent Arena score and median cost per task (data from 11/19/2026) |
| `exemplos/tentativas-exemplo.csv` | **Fictional** test example (not a measurement) |
| `guia/` | The guide in PT, EN, and ES (GitHub Pages) |

### Attempt CSV Format

One row per attempt:

| Column | What to Enter |
|---|---|
| `modelo` | Same as the name in `dados/precos-2026-11-19.csv` (e.g., `Gemini 4 Argon`) |
| `execucao` | Label for each time you gave the task from scratch (1, 2, 3…). Corrections for the same run add to its cost and count as one delivery |
| `tokens_entrada`, `tokens_saida` | Tokens spent on the attempt |
| `custo_usd` | Amount charged, if shown on the dashboard. Blank = calculated from tokens and the table |
| `aprovada` | `sim` or `não`. A run counts as a delivery if any attempt in it was approved |

Missing cost is never treated as zero: the model appears as “no cost” and is excluded from the comparison.

### How the Calculation Works

`cost per successful delivery = sum of the cost of all attempts ÷ number of approved runs`

To test with ready-made tasks and fictional data, use the Gemini 4 lab protocol: [protocolo.md](https://github.com/inematds/gemini-4-na-pratica/blob/main/laboratorio/protocolo.md).

## Sources

- Google: [pricing](https://aistudio.google.com/docs/pricing) · [Neon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) · [Argon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-argon/) · [Hydrogen](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/)
- Anthropic: [pricing](https://platform.claude.com/docs/en/about-claude/pricing) · [Haiku 5.5](https://www.anthropic.com/claude-haiku-5-5)
- OpenAI: [pricing](https://developers.openai.com/api/docs/pricing) · [GPT-6.2](https://openai.com/index/introducing-gpt-6-2-astra-sol/) · [GPT-6 Luna](https://developers.openai.com/api/docs/models/gpt-6-luna)
- [Agent Arena](https://arena.ai/leaderboard/agent): Google at High effort, Anthropic and OpenAI at Max; cost = median cost per task over the last 14 days; score is not an accuracy percentage.

## The Process, from Start to Finish

| # | Step | Command | Who |
|---|---|---|---|
| 1 | Check prices and leaderboard against official sources and update `dados/*.csv` | — | 🧠 session with Nei |
| 2 | Check the tables and calculation | `python3 calcular.py --precos` / `--arena` / `exemplos/tentativas-exemplo.csv` | ⚙️ script |
| 3 | Write the PT guide (`guia/index.html`) and generate the cover and banners | `gerar-capa.cjs`, `gerar-banner.sh` | 🧠 + ⚙️ Codex image_gen |
| 4 | Translate the guide and README to EN/ES | `traduz-pagina-codex.py html` / `readme` | ⚙️ central translator |
| 5 | Independent review of the guide | `revisor-nota.py registra --fluxo guia` | 🤖 new reviewer |
| 6 | Publish: commit + push (GitHub Pages via Actions) | `git push` | 🧠 |
| 7 | Portal, search, and PRO catalog | skill `atualiza-portal` | 🧠 |
| 8 | Topic on INEMA.LLMS | skill `postar-telegram` | 🧠 |
| 9 | Comparison video on lives4 and embed in the guide (3 languages) | `yt-pub-x3` | ⚙️ x3 + 🧠 |

Free on inema.club, directly on the internet. MIT License.
