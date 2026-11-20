# ⚖️ Which AI to Use - GEMINI - GPT - CLAUDE

**🇧🇷 [Português](README.md) · 🇺🇸 [English](README.en.md) · 🇪🇸 [Español](README.es.md)**

[![Which AI costs less](guia/assets/banner.jpg)](https://inematds.github.io/qual-ia-usar/guia/en/)

## What It Is

This project compares ten AI models from three companies: Google’s Gemini 4 (Neon, Argon, and Hydrogen), Anthropic’s Claude (Fable, Opus, Sonnet, and Haiku), and the OpenAI models used by Codex (Astra, Sol, and Luna). It brings together official pricing tables and the Agent Arena leaderboard, a public ranking that measures AI agents performing real tasks, checked on 19/11/2026. It’s for people who pay for AI and want to choose without wasting money. You don’t need anything to read it; to test it with your own task, you just need Claude Code or Codex.

## 📖 Guide

Complete guide, in plain language: **https://inematds.github.io/qual-ia-usar/guia/en/**

## The Idea in One Line

The cheapest AI in the pricing table can end up costing more on your bill. What matters is the **cost per correct deliverable**: everything you paid for, including failed attempts, divided by the tasks that were completed correctly.

## The Winner in Each Tier (19/11/2026)

Price in US$ per million tokens (input / output). Score and cost per task: Agent Arena.

| Tier | Google | Anthropic | OpenAI |
|---|---|---|---|
| Complex work | Gemini 4 Neon · 3 / 15 · score 1333 · US$ 2,60 per task | Claude Opus 5.5 · 4 / 20 · 1336 · US$ 5,98 | GPT-6.2 Astra · 8 / 40 · 1291 · US$ 3,11 |
| Everyday use | Gemini 4 Argon · 2 / 10 (4 / 20 starting 1º/12) · 1229 · US$ 0,66 | Claude Sonnet 5.5 · 2 / 10 · 1296 · US$ 3,27 | GPT-6.2 Sol · 2 / 10 · 1241 · US$ 0,96 |
| High volume | Gemini 4 Hydrogen · 1,50 / 7,50 · 1271 (preliminary) · US$ 1,50 | Claude Haiku 5.5 · 0,10 / 0,50 · no score | GPT-6 Luna · 0,10 / 0,50 · no score |

Outside these tiers: **Claude Fable 5.2** (US$ 8 / 40) leads the leaderboard with a score of 1448 and costs US$ 9,16 per task.

- **Complex:** Neon nearly ties with Opus and costs less than half as much per task.
- **Everyday use:** all three charge the same per token; per task, Argon costs less and Sonnet has the highest score.
- **Volume:** Haiku and Luna charge 15 times less per token than Hydrogen; their quality can only be found out by testing.
- **Within Google:** Hydrogen is cheaper per token than Argon, but cost more than twice as much per task.

What this comparison doesn’t promise: the tier numbers are the published figures (the test below covers one task and seven models), the leaderboard measures agents performing tasks in general, not your task, and everything changes over time.

## How to Get Started (No Programming)

Open Claude Code or Codex in one of your folders and paste:

```text
Read the "Qual IA usar" project at https://github.com/inematds/qual-ia-usar (the README explains the method and calculator).
I want to know which AI costs less per correct deliverable for one of my tasks: [describe the task and what "done correctly" means].
1. Tell me, in plain English, which 3 or 4 models are worth testing for this task and why.
2. Propose a small test: how many times to run each model and how much it should cost.
3. Don’t call any model or spend anything before I say yes.
After I say yes, set up the task in the kit format (kit/testar.py), run the test, and show me the report.
```

## Test Kit: Your Task Across All the AIs

You describe the task and what “done correctly” means. The kit runs the same task on each AI several times, evaluates each response (an AI judge and, if you want, an automatic checker), and returns a report: how many were correct, time, and cost per correct deliverable.

**Real test (19/11/2026, receipt task, 2 runs each, via subscription):**

| Model | Correct | US$ per correct deliverable | Median time |
|---|---:|---:|---:|
| GPT-6 Luna | 2/2 | 0,0001 | 7 s |
| Claude Haiku 5.5 | 2/2 | 0,0004 | 6 s |
| GPT-6.2 Sol | 2/2 | 0,0014 | 9 s |
| Claude Sonnet 5.5 | 2/2 | 0,0031 | 4 s |
| GPT-6.2 Astra | 2/2 | 0,0064 | 10 s |
| Claude Opus 5.5 | 2/2 | 0,0086 | 7 s |
| Claude Fable 5.2 | 2/2 | 0,0181 | 5 s |

On a simple task, everyone gets it right, so the cheapest wins: Fable cost about 270 times as much as Luna for the same deliverable. The three Gemini models were left out of this test (Gemini CLI wasn’t installed). Full report: [resultados/2026-11-19-2150-comprovantes](resultados/2026-11-19-2150-comprovantes/relatorio.md).

---

## Technical Installation

You only need Python 3 (no extra libraries).

```bash
git clone https://github.com/inematds/qual-ia-usar
cd qual-ia-usar
python3 calcular.py --precos                              # price table per token
python3 calcular.py --arena                               # Agent Arena leaderboard + points per dollar
python3 calcular.py exemplos/tentativas-exemplo.csv       # fictional test example
```

### Test Kit

```bash
python3 kit/testar.py kit/exemplo-comprovantes --simular              # shows the plan, calls nothing
python3 kit/testar.py kit/exemplo-comprovantes --so "Claude,GPT" --repeticoes 2
python3 kit/testar.py minha-tarefa/ --juiz claude-cli:claude-sonnet-5-5
python3 kit/teste_vias_api.py                                         # tests API methods against a fake server
```

**The task** is a folder containing `tarefa.json`:

```json
{"nome": "comprovantes",
 "pedido_arquivo": "pedido.md",
 "criterio": "what 'done correctly' means, point by point",
 "verificar": "python3 verificar.py",
 "repeticoes": 3}
```

`verificar` is optional: a command that receives the response path and exits with 0 when it’s correct. A response only counts as correct if it passes the checker **and** the judge.

**Models** are listed in `kit/motores.json` (`modelo` matches the name in `dados/precos-*.csv`, `via`, `id`). Methods:

| Method | How it’s called | Requires |
|---|---|---|
| `claude-cli` | `claude -p`, no tools | Claude Code logged in (subscription) |
| `codex-cli` | `codex exec`, read-only sandbox | Codex logged in (subscription) |
| `gemini-cli` | `gemini -p` | Gemini CLI installed and logged in |
| `api-anthropic`, `api-openai`, `api-google`, `openrouter` | HTTP API | `ANTHROPIC_API_KEY`, `OPENAI_API_KEY`, `GEMINI_API_KEY`, `OPENROUTER_API_KEY` |

Cost is calculated using measured tokens × the official price table. Claude Code, Codex, and Gemini CLI add their own instructions to each prompt; the kit measures this addition once per model and subtracts it (the raw number is in the `tokens_entrada_bruto` column). With a subscription, you don’t pay per task: read the cost as “what it would cost per use.” The API methods and `gemini-cli` method were tested only against a fake server; check each model’s `id` in the company’s documentation.

Output in `resultados/<data>-<nome>/`: the responses, `tentativas.csv` (which `calcular.py` also reads), and `relatorio.md`.

### Files

| File | What it is |
|---|---|
| `calcular.py` | Calculates cost per correct deliverable from a CSV of attempts |
| `dados/precos-2026-11-19.csv` | Official prices per million tokens, with the source for each row |
| `dados/arena-2026-11-19.csv` | Agent Arena score and median cost per task (snapshot from 19/11/2026) |
| `exemplos/tentativas-exemplo.csv` | **Fictional** test example (not a measurement) |
| `kit/testar.py` | Test kit: runs the task on each AI, evaluates it, and calculates cost per correct deliverable |
| `kit/motores.json` | List of models and how to call each one |
| `kit/exemplo-comprovantes/` | Example task with an automatic checker |
| `resultados/` | Reports from tests already run |
| `guia/` | The guide in PT, EN, and ES (GitHub Pages) |

### Attempt CSV Format

One row per attempt:

| Column | What goes in it |
|---|---|
| `modelo` | Matches the name in `dados/precos-2026-11-19.csv` (e.g. `Gemini 4 Argon`) |
| `execucao` | Label for each time you gave the task from scratch (1, 2, 3…). Fixes made during the same run add to the cost and count as one deliverable |
| `tokens_entrada`, `tokens_saida` | Tokens spent on the attempt |
| `custo_usd` | Amount charged, if the dashboard shows it. Empty = calculated from tokens and the table |
| `aprovada` | `sim` or `não`. The run counts as a deliverable if any of its attempts was approved |

Missing cost never becomes zero: the model appears as “no cost” and is excluded from the comparison.

### How the Calculation Works

`cost per correct deliverable = total cost of all attempts ÷ number of approved runs`

To test with ready-made tasks and fictional data, use the Gemini 4 lab protocol: [protocolo.md](https://github.com/inematds/gemini-4-na-pratica/blob/main/laboratorio/protocolo.md).

## Sources

- Google: [pricing](https://aistudio.google.com/docs/pricing) · [Neon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) · [Argon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-argon/) · [Hydrogen](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/)
- Anthropic: [pricing](https://platform.claude.com/docs/en/about-claude/pricing) · [Haiku 5.5](https://www.anthropic.com/claude-haiku-5-5)
- OpenAI: [pricing](https://developers.openai.com/api/docs/pricing) · [GPT-6.2](https://openai.com/index/introducing-gpt-6-2-astra-sol/) · [GPT-6 Luna](https://developers.openai.com/api/docs/models/gpt-6-luna)
- [Agent Arena](https://arena.ai/leaderboard/agent): Google at High effort, Anthropic and OpenAI at Max; cost = median per task over the last 14 days; score is not an accuracy percentage.

## The Process, From Start to Finish

| # | Step | Command | Who |
|---|---|---|---|
| 1 | Check prices and leaderboard on official sources and update `dados/*.csv` | — | 🧠 session with Nei |
| 2 | Check the tables and calculations | `python3 calcular.py --precos` / `--arena` / `exemplos/tentativas-exemplo.csv` | ⚙️ script |
| 3 | Write the PT guide (`guia/index.html`) and generate the cover and banners | `gerar-capa.cjs`, `gerar-banner.sh` | 🧠 + ⚙️ Codex image_gen |
| 4 | Translate the guide and README into EN/ES | `traduz-pagina-codex.py html` / `readme` | ⚙️ central translator |
| 5 | Independent review of the guide | `revisor-nota.py registra --fluxo guia` | 🤖 new reviewer |
| 6 | Publish: commit + push (GitHub Pages via Actions) | `git push` | 🧠 |
| 7 | Portal, search, and PRO catalog | skill `atualiza-portal` | 🧠 |
| 8 | Post a topic on INEMA.LLMS | skill `postar-telegram` | 🧠 |
| 9 | Comparison video on lives4 and embed in the guide (3 languages) | `yt-pub-x3` | ⚙️ x3 + 🧠 |

Free on inema.club, right on the internet. MIT License.
