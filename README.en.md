# ⚖️ Which AI to use - GEMINI - GPT - CLAUDE

**🇧🇷 [Português](README.md) · 🇺🇸 [English](README.en.md) · 🇪🇸 [Español](README.es.md)**

[![Which AI costs less](guia/assets/banner-en.jpg)](https://inematds.github.io/qual-ia-usar/guia/en/)

## What it is

This project compares ten AI models from three companies: Google's Gemini 4 (Neon, Argon, and Hydrogen), Anthropic's Claude (Fable, Opus, Sonnet, and Haiku), and the OpenAI models used by Codex (Astra, Sol, and Luna). It brings together official pricing tables and the Agent Arena leaderboard, a public ranking that measures AI agents performing real tasks, version checked on Nov 19, 2026. It's for people who pay for AI and want to choose without wasting money. You don't need anything to read it. To test with your own task, all you need are the apps you already use (ChatGPT, Claude, or Gemini), or the testing kit, which runs the same task across every AI you enable and tells you which got more right for less.

## 📖 Guide

Complete guide, in plain language: **https://inematds.github.io/qual-ia-usar/guia/en/**

## The idea in one line

The cheapest AI in the table can end up costing more on your bill. What matters is the **cost per successful task**: everything you paid, including failed attempts, divided by the tasks that were completed correctly.

## Who wins in each tier (Nov 19, 2026)

Price in US$ per million tokens (input / output). Score and cost per task: Agent Arena.

| Tier | Google | Anthropic | OpenAI |
|---|---|---|---|
| Complex work | Gemini 4 Neon · 3 / 15 · Score 1333 · US$ 2.60 per task | Claude Opus 5.5 · 4 / 20 · 1336 · US$ 5.98 | GPT-6.2 Astra · 8 / 40 · 1291 · US$ 3.11 |
| Everyday work | Gemini 4 Argon · 2 / 10 (4 / 20 starting Dec 1) · 1229 · US$ 0.66 | Claude Sonnet 5.5 · 2 / 10 · 1296 · US$ 3.27 | GPT-6.2 Sol · 2 / 10 · 1241 · US$ 0.96 |
| High volume | Gemini 4 Hydrogen · 1.50 / 7.50 · 1271 (preliminary) · US$ 1.50 | Claude Haiku 5.5 · 0.10 / 0.50 · no score | GPT-6 Luna · 0.10 / 0.50 · no score |

Outside the tiers: **Claude Fable 5.2** (US$ 8 / 40) leads the leaderboard with a score of 1448 and costs US$ 9.16 per task.

- **Complex work:** Neon nearly ties with Opus and costs less than half as much per task.
- **Everyday work:** all three charge the same per token; per task, Argon costs less and Sonnet has the highest score.
- **High volume:** Haiku and Luna charge 15 times less per token than Hydrogen; their quality can only be found out by testing.
- **Within Google:** Hydrogen is cheaper per token than Argon, but cost more than twice as much per task.

What this comparison doesn't promise: the tier figures are published numbers (the test below covers one task and seven models), the leaderboard measures agent tasks in general, not yours, and everything changes over time.

## How to get started (without programming)

Open Claude Code or Codex in one of your folders and paste:

```text
Read the project "Which AI to use" at https://github.com/inematds/qual-ia-usar (the README explains the testing kit in kit/testar.py).
I want to know which AI costs less per successful task for one of my tasks: [describe the task and what "done right" means].
1. Tell me, in plain English, which 3 or 4 models are worth testing for this task and why.
2. Propose a small test: how many times to run each model and how much it should cost.
3. Don't call any model or spend anything before I say yes.
After I say yes, set up the task in the kit's format (kit/testar.py), run the test, and show me the report.
```

## Testing kit: your task across all AIs

You describe the task and what "done right" means. The kit runs the same task on each AI several times, evaluates each response (an AI judge and, if you want, an automatic checker), and returns a report: how many were correct, time, and cost per successful task.

**Real test (Nov 19, 2026, receipt task, 2 runs each, by subscription):**

| Model | Correct | US$ per successful task | Median time |
|---|---:|---:|---:|
| GPT-6 Luna | 2/2 | 0.00008 | 9 s |
| Claude Haiku 5.5 | 2/2 | 0.00036 | 6 s |
| GPT-6.2 Sol | 2/2 | 0.00201 | 10 s |
| Claude Sonnet 5.5 | 2/2 | 0.00311 | 4 s |
| GPT-6.2 Astra | 2/2 | 0.00644 | 10 s |
| Claude Opus 5.5 | 2/2 | 0.00856 | 7 s |
| Claude Fable 5.2 | 2/2 | 0.01572 | 5 s |

On a simple task, every model gets it right, so the cheapest wins: Fable cost about 200 times as much as Luna for the same successful task. The three Gemini models were left out of this test (Gemini CLI wasn't installed). Full report: [resultados/2026-11-19-2200-comprovantes](resultados/2026-11-19-2200-comprovantes/relatorio.md) (in Portuguese).

---

## Technical installation

You only need Python 3 (no extra libraries).

```bash
git clone https://github.com/inematds/qual-ia-usar
cd qual-ia-usar
python3 calcular.py --precos                              # token price table
python3 calcular.py --arena                               # Agent Arena leaderboard + points per dollar
python3 calcular.py exemplos/tentativas-exemplo.csv       # fictional test example
```

### Testing kit

```bash
python3 kit/testar.py kit/exemplo-comprovantes --simular              # shows the plan, doesn't call anything
python3 kit/testar.py kit/exemplo-comprovantes --so "Claude,GPT" --repeticoes 2
python3 kit/testar.py minha-tarefa/ --juiz claude-cli:claude-sonnet-5-5
python3 kit/teste_vias_api.py                                         # tests the API routes on a fake server
```

**The task** is a folder with `tarefa.json`:

```json
{"nome": "comprovantes",
 "pedido_arquivo": "pedido.md",
 "criterio": "how to tell it was done right, point by point",
 "verificar": "python3 verificar.py",
 "repeticoes": 3}
```

`verificar` is optional: a command that receives the response path and exits with 0 when it is correct. A response only counts as correct if it passes both the checker **and** the judge.

**Models** are listed in `kit/motores.json` (`modelo` is the same as the name in `dados/precos-*.csv`, `via`, `id`). Routes:

| Route | How it is called | Requires |
|---|---|---|
| `claude-cli` | `claude -p`, no tools | Claude Code logged in (subscription) |
| `codex-cli` | `codex exec`, read-only sandbox | Codex logged in (subscription) |
| `gemini-cli` | `gemini -p` | Gemini CLI installed and logged in |
| `api-anthropic`, `api-openai`, `api-google`, `openrouter` | HTTP API | `ANTHROPIC_API_KEY`, `OPENAI_API_KEY`, `GEMINI_API_KEY`, `OPENROUTER_API_KEY` |

Cost is calculated from measured tokens × the official price table. Claude Code, Codex, and Gemini CLI add their own instructions to each prompt; the kit measures this added amount once per model and subtracts it (the raw number is in the `tokens_entrada_bruto` column). With a subscription, you don't pay per task: read the cost as "what it would cost on a pay-as-you-go basis." The API routes and `gemini-cli` route were tested only against a fake server; check each model's `id` in the company's documentation.

Output in `resultados/<data>-<nome>/`: responses, `tentativas.csv` (which `calcular.py` also reads), and `relatorio.md`.

### Files

| File | What it is |
|---|---|
| `calcular.py` | Calculates the cost per successful task from a CSV of attempts |
| `dados/precos-2026-11-19.csv` | Official prices per million tokens, with the source for each row (in Portuguese) |
| `dados/arena-2026-11-19.csv` | Agent Arena score and median cost per task (snapshot from Nov 19, 2026) (in Portuguese) |
| `exemplos/tentativas-exemplo.csv` | **Fictional** test example (not a measurement) |
| `kit/testar.py` | Testing kit: runs the task on each AI, evaluates it, and calculates the cost per successful task |
| `kit/motores.json` | List of models and how to call each one |
| `kit/exemplo-comprovantes/` | Example task with an automatic checker |
| `resultados/` | Reports from tests already run |
| `guia/` | Guide in PT, EN, and ES (GitHub Pages) |

### Attempt CSV format

One row per attempt:

| Column | What it contains |
|---|---|
| `modelo` | Same as the name in `dados/precos-2026-11-19.csv` (e.g., `Gemini 4 Argon`) |
| `execucao` | Label for each time you gave the task from scratch (1, 2, 3…). Corrections in the same run add to the cost and count as one task |
| `tokens_entrada`, `tokens_saida` | Tokens spent on the attempt |
| `custo_usd` | Amount charged, if shown in the dashboard. Empty = calculated from tokens and the table |
| `aprovada` | `sim` or `não`. A run counts as a successful task if any attempt in it was approved |

Missing cost never becomes zero: the model appears as "no cost" and is excluded from the comparison.

### How the calculation works

`cost per successful task = total cost of all attempts ÷ number of approved runs`

To test with ready-made tasks and fictional data, use the Gemini 4 lab protocol: [protocolo.md](https://github.com/inematds/gemini-4-na-pratica/blob/main/laboratorio/protocolo.md).

## Sources

- Google: [pricing](https://aistudio.google.com/docs/pricing) · [Neon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) · [Argon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-argon/) · [Hydrogen](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/)
- Anthropic: [pricing](https://platform.claude.com/docs/en/about-claude/pricing) · [Haiku 5.5](https://www.anthropic.com/claude-haiku-5-5)
- OpenAI: [pricing](https://developers.openai.com/api/docs/pricing) · [GPT-6.2](https://openai.com/index/introducing-gpt-6-2-astra-sol/) · [GPT-6 Luna](https://developers.openai.com/api/docs/models/gpt-6-luna)
- [Agent Arena](https://arena.ai/leaderboard/agent): Google at High effort, Anthropic and OpenAI at Max; cost = median per task over the last 14 days; score is not an accuracy percentage.

## The process, from start to finish

| # | Step | Command | Who |
|---|---|---|---|
| 1 | Check prices and leaderboard in official sources and update `dados/*.csv` | — | 🧠 session with Nei |
| 2 | Check the tables and calculation | `python3 calcular.py --precos` / `--arena` / `exemplos/tentativas-exemplo.csv` | ⚙️ script |
| 3 | Write the PT guide (`guia/index.html`) and generate the cover and banners | `gerar-capa.cjs`, `gerar-banner.sh` | 🧠 + ⚙️ Codex image_gen |
| 4 | Translate the guide and README to EN/ES | `traduz-pagina-codex.py html` / `readme` | ⚙️ central translator |
| 5 | Independent guide review | `revisor-nota.py registra --fluxo guia` | 🤖 new reviewer |
| 6 | Publish: commit + push (GitHub Pages via Actions) | `git push` | 🧠 |
| 7 | Portal, search, and PRO catalog | `atualiza-portal` skill | 🧠 |
| 8 | Topic in INEMA.LLMS | `postar-telegram` skill | 🧠 |
| 9 | Comparison video on lives4 and embed in the guide (3 languages) | `yt-pub-x3` | ⚙️ x3 + 🧠 |

Free on inema.club, directly on the internet. MIT License.
