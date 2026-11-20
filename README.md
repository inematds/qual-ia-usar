# ⚖️ Qual IA usar - GEMINI - GPT - CLAUDE

**🇧🇷 [Português](README.md) · 🇺🇸 [English](README.en.md) · 🇪🇸 [Español](README.es.md)**

[![Qual IA sai mais barata](guia/assets/banner.jpg)](https://inematds.github.io/qual-ia-usar/guia/)

## O que é

Este projeto compara dez modelos de IA de três empresas: o Gemini 4 do Google (Neon, Argon e Hydrogen), o Claude da Anthropic (Fable, Opus, Sonnet e Haiku) e os modelos da OpenAI que o Codex usa (Astra, Sol e Luna). Ele junta as tabelas oficiais de preço e o placar do Agent Arena, um ranking público que mede agentes de IA fazendo tarefas reais, consultados em 19/11/2026. Serve para quem paga IA e quer escolher sem desperdiçar dinheiro. Para ler, não precisa de nada; para testar com a sua própria tarefa, basta o Claude Code ou o Codex.

## 📖 Guia

Guia completo, em linguagem simples: **https://inematds.github.io/qual-ia-usar/guia/**

## A ideia em uma linha

A IA mais barata na tabela pode sair mais cara na sua conta. O que importa é o **custo por entrega certa**: tudo o que você pagou, inclusive as tentativas erradas, dividido pelas tarefas que ficaram certas.

## Quem vence em cada faixa (19/11/2026)

Preço em US$ por milhão de tokens (entrada / saída). Nota e custo por tarefa: Agent Arena.

| Faixa | Google | Anthropic | OpenAI |
|---|---|---|---|
| Trabalho complexo | Gemini 4 Neon · 3 / 15 · nota 1333 · US$ 2,60 por tarefa | Claude Opus 5.5 · 4 / 20 · 1336 · US$ 5,98 | GPT-6.2 Astra · 8 / 40 · 1291 · US$ 3,11 |
| Dia a dia | Gemini 4 Argon · 2 / 10 (4 / 20 a partir de 1º/12) · 1229 · US$ 0,66 | Claude Sonnet 5.5 · 2 / 10 · 1296 · US$ 3,27 | GPT-6.2 Sol · 2 / 10 · 1241 · US$ 0,96 |
| Grande volume | Gemini 4 Hydrogen · 1,50 / 7,50 · 1271 (preliminar) · US$ 1,50 | Claude Haiku 5.5 · 0,10 / 0,50 · sem nota | GPT-6 Luna · 0,10 / 0,50 · sem nota |

Fora das faixas: o **Claude Fable 5.2** (US$ 8 / 40) lidera o placar com nota 1448 e custa US$ 9,16 por tarefa.

- **Complexo:** o Neon quase empata com o Opus e custa menos da metade por tarefa.
- **Dia a dia:** os três cobram igual por token; por tarefa, o Argon sai mais barato e o Sonnet tem a melhor nota.
- **Volume:** Haiku e Luna cobram 15 vezes menos por token que o Hydrogen; a qualidade deles só se descobre testando.
- **Dentro do Google:** o Hydrogen é mais barato por token que o Argon, mas custou mais que o dobro por tarefa.

O que este comparativo não promete: os números são os publicados (nenhum teste próprio com os dez modelos ainda), o placar mede tarefas de agentes em geral e não a sua, e tudo muda com o tempo.

## Como começar (sem programar)

Abra o Claude Code ou o Codex numa pasta sua e cole:

```text
Leia o projeto "Qual IA usar" em https://github.com/inematds/qual-ia-usar (o README explica o método e a calculadora).
Eu quero saber qual IA sai mais barata por entrega certa numa tarefa minha: [descreva a tarefa e como é "ficou certo"].
1. Me diga, em português simples, quais 3 ou 4 modelos valem testar para essa tarefa e por quê.
2. Proponha um teste pequeno: quantas vezes rodar cada modelo e quanto isso deve custar.
3. Não chame nenhum modelo nem gaste nada antes de eu dizer sim.
Depois do meu sim, registre cada tentativa no formato do projeto, rode a calculadora e me mostre o resultado.
```

---

## Instalação técnica

Só precisa do Python 3 (nenhuma biblioteca extra).

```bash
git clone https://github.com/inematds/qual-ia-usar
cd qual-ia-usar
python3 calcular.py --precos                              # tabela de preços por token
python3 calcular.py --arena                               # placar do Agent Arena + pontos por dólar
python3 calcular.py exemplos/tentativas-exemplo.csv       # exemplo fictício de teste
```

### Arquivos

| Arquivo | O que é |
|---|---|
| `calcular.py` | Calcula o custo por entrega certa a partir de um CSV de tentativas |
| `dados/precos-2026-11-19.csv` | Preços oficiais por milhão de tokens, com a fonte de cada linha |
| `dados/arena-2026-11-19.csv` | Nota e custo mediano por tarefa no Agent Arena (recorte de 19/11/2026) |
| `exemplos/tentativas-exemplo.csv` | Exemplo **fictício** de teste (não é medição) |
| `guia/` | O guia em PT, EN e ES (GitHub Pages) |

### Formato do CSV de tentativas

Uma linha por tentativa:

| Coluna | O que vai |
|---|---|
| `modelo` | Igual ao nome em `dados/precos-2026-11-19.csv` (ex.: `Gemini 4 Argon`) |
| `execucao` | Rótulo de cada vez que você deu a tarefa do zero (1, 2, 3…). Correções da mesma execução somam custo e contam uma entrega |
| `tokens_entrada`, `tokens_saida` | Tokens gastos na tentativa |
| `custo_usd` | Valor cobrado, se o painel mostrar. Vazio = calcula pelos tokens e pela tabela |
| `aprovada` | `sim` ou `não`. A execução conta como entrega se alguma tentativa dela foi aprovada |

Custo ausente nunca vira zero: o modelo aparece como "sem custo" e fica fora da comparação.

### Como a conta é feita

`custo por entrega certa = soma do custo de todas as tentativas ÷ número de execuções aprovadas`

Para testar com tarefas prontas e dados fictícios, use o protocolo do laboratório do Gemini 4: [protocolo.md](https://github.com/inematds/gemini-4-na-pratica/blob/main/laboratorio/protocolo.md).

## Fontes

- Google: [preços](https://aistudio.google.com/docs/pricing) · [Neon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) · [Argon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-argon/) · [Hydrogen](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/)
- Anthropic: [preços](https://platform.claude.com/docs/en/about-claude/pricing) · [Haiku 5.5](https://www.anthropic.com/claude-haiku-5-5)
- OpenAI: [preços](https://developers.openai.com/api/docs/pricing) · [GPT-6.2](https://openai.com/index/introducing-gpt-6-2-astra-sol/) · [GPT-6 Luna](https://developers.openai.com/api/docs/models/gpt-6-luna)
- [Agent Arena](https://arena.ai/leaderboard/agent): Google em esforço High, Anthropic e OpenAI em Max; custo = mediana por tarefa dos últimos 14 dias; nota não é porcentagem de acerto.

## O processo, do início ao fim

| # | Passo | Comando | Quem |
|---|---|---|---|
| 1 | Conferir preços e placar nas fontes oficiais e atualizar `dados/*.csv` | — | 🧠 sessão com o Nei |
| 2 | Conferir as tabelas e a conta | `python3 calcular.py --precos` / `--arena` / `exemplos/tentativas-exemplo.csv` | ⚙️ script |
| 3 | Escrever o guia PT (`guia/index.html`) e gerar capa e banners | `gerar-capa.cjs`, `gerar-banner.sh` | 🧠 + ⚙️ Codex image_gen |
| 4 | Traduzir guia e README para EN/ES | `traduz-pagina-codex.py html` / `readme` | ⚙️ tradutor central |
| 5 | Revisão independente do guia | `revisor-nota.py registra --fluxo guia` | 🤖 revisor novo |
| 6 | Publicar: commit + push (GitHub Pages via Actions) | `git push` | 🧠 |
| 7 | Portal, busca e catálogo PRO | skill `atualiza-portal` | 🧠 |
| 8 | Tópico no INEMA.LLMS | skill `postar-telegram` | 🧠 |
| 9 | Vídeo do comparativo no lives4 e embed no guia (3 idiomas) | `yt-pub-x3` | ⚙️ x3 + 🧠 |

Grátis no inema.club, direto na internet. Licença MIT.
