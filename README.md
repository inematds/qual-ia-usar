# ⚖️ Qual IA usar - GEMINI - GPT - CLAUDE

**🇧🇷 [Português](README.md) · 🇺🇸 [English](README.en.md) · 🇪🇸 [Español](README.es.md)**

[![Qual IA sai mais barata](guia/assets/banner.jpg)](https://inematds.github.io/qual-ia-usar/guia/)

## O que é

Este projeto compara dez modelos de IA de três empresas: o Gemini 4 do Google (Neon, Argon e Hydrogen), o Claude da Anthropic (Fable, Opus, Sonnet e Haiku) e os modelos da OpenAI que o Codex usa (Astra, Sol e Luna). Ele junta as tabelas oficiais de preço e o placar do Agent Arena, um ranking público que mede agentes de IA fazendo tarefas reais, consultados em 19/11/2026. Serve para quem paga IA e quer escolher sem desperdiçar dinheiro. Para ler, não precisa de nada. Para testar com a sua própria tarefa, bastam os apps que você já usa (ChatGPT, Claude ou Gemini), ou o kit de testes, que roda a mesma tarefa em todas as IAs que você ligar e diz qual acertou mais e gastou menos.

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

O que este comparativo não promete: os números das faixas são os publicados (o teste próprio, abaixo, cobre uma tarefa e sete modelos), o placar mede tarefas de agentes em geral e não a sua, e tudo muda com o tempo.

## Todas as comparações (quadro)

Quatro comparações entre Google, Anthropic e OpenAI, de 19 e 20/11/2026. Só os números.

| Comparação | O que foi medido | Google (Gemini 4) | Anthropic (Claude) | OpenAI (GPT) |
|---|---|---|---|---|
| **1. Preço oficial** (10 modelos) | US$ por milhão de tokens, entrada / saída | Neon 3 / 15 · Argon 2 / 10 · Hydrogen 1,50 / 7,50 | Fable 8 / 40 · Opus 4 / 20 · Sonnet 2 / 10 · Haiku 0,10 / 0,50 | Astra 8 / 40 · Sol 2 / 10 · Luna 0,10 / 0,50 |
| **2. Placar do Agent Arena** (8 com nota) | nota · US$ por tarefa | Neon 1333 · 2,60 · Hydrogen 1271 · 1,50 · Argon 1229 · 0,66 | Fable 1448 · 9,16 · Opus 1336 · 5,98 · Sonnet 1296 · 3,27 | Astra 1291 · 3,11 · Sol 1241 · 0,96 |
| **3. Kit de testes** (comprovantes, 10 × 2, pela assinatura) | acertos · ¢ por entrega certa · tempo | 3 de 3 · 1,92–3,62 ¢ · 12–16 s (esforço alto) | 4 de 4 · 0,038–1,55 ¢ · 4–6 s | 3 de 3 · 0,008–0,66 ¢ · 7–11 s |
| **4. Análise de um documento longo** (182 KB, mesmo pedido, conteúdo interno não publicado) | tempo · contagens erradas · nota de qualidade (nossa) | Neon: 5,5 min · 3 · 6,5 | Fable 5.2: 14 min · 0 · 9 | Astra: 4,5 min · 0 · 8 |

- **Qualidade:** na análise longa, o Fable foi o mais rigoroso e o Astra, o melhor custo-benefício. O Neon foi o mais extenso, mas errou contagens e tirou conclusões que os outros dois refutaram.
- **Custo:** na tarefa simples todos acertaram e o GPT-6 Luna foi o mais barato. No esforço alto, os Gemini pensam mais e saíram os mais caros por entrega.
- **Velocidade:** o Claude Sonnet foi o mais rápido na tarefa simples (4 s), e o Astra na análise longa (4,5 min); o Fable levou três vezes mais.
- A nota de qualidade da análise é avaliação nossa: o Astra e o Fable conferiram os números do Neon contra o documento e chegaram às mesmas correções. O Neon respondeu primeiro, e os outros dois leram a análise dele. Uma tarefa e um documento não bastam para dizer qual modelo é melhor em geral.

## Como começar (sem programar)

Abra o Claude Code ou o Codex numa pasta sua e cole:

```text
Leia o projeto "Qual IA usar" em https://github.com/inematds/qual-ia-usar (o README explica o kit de testes em kit/testar.py).
Eu quero saber qual IA sai mais barata por entrega certa numa tarefa minha: [descreva a tarefa e como é "ficou certo"].
1. Me diga, em português simples, quais 3 ou 4 modelos valem testar para essa tarefa e por quê.
2. Proponha um teste pequeno: quantas vezes rodar cada modelo e quanto isso deve custar.
3. Não chame nenhum modelo nem gaste nada antes de eu dizer sim.
Depois do meu sim, monte a tarefa no formato do kit (kit/testar.py), rode o teste e me mostre o relatório.
```

## Kit de testes: a sua tarefa em todas as IAs

Você descreve a tarefa e como é "ficou certo". O kit roda a mesma tarefa em cada IA várias vezes, avalia cada resposta (um juiz de IA e, se você quiser, um verificador automático) e devolve um relatório: quantas ficaram certas, tempo e custo por entrega certa.

**Teste real (19/11/2026, tarefa dos comprovantes, 2 vezes cada, todos pela assinatura: Claude pelo Claude Code, GPT pelo Codex, Gemini pelo Google AI Pro via Antigravity CLI):**

| Modelo | Certas | US$ por entrega certa | Tempo mediano |
|---|---:|---:|---:|
| GPT-6 Luna | 2/2 | 0,00008 | 7 s |
| Claude Haiku 5.5 | 2/2 | 0,00038 | 6 s |
| GPT-6.2 Sol | 2/2 | 0,00155 | 9 s |
| Claude Sonnet 5.5 | 2/2 | 0,00316 | 4 s |
| GPT-6.2 Astra | 2/2 | 0,00656 | 11 s |
| Claude Opus 5.5 | 2/2 | 0,00813 | 6 s |
| Claude Fable 5.2 | 2/2 | 0,01552 | 5 s |
| Gemini 4 Argon (high) | 2/2 | 0,01917 | 16 s |
| Gemini 4 Hydrogen (high) | 2/2 | 0,02211 | 12 s |
| Gemini 4 Neon (high) | 2/2 | 0,03616 | 16 s |

Numa tarefa simples todos acertam, e aí o mais barato vence. Os três Gemini rodaram no esforço **high** (o mesmo do placar) e pensam bastante antes de responder (1.600 a 2.900 tokens de saída); Claude e GPT rodaram no esforço padrão de cada assistente. Pela API, no esforço padrão, o Hydrogen custou US$ 0,0087 por entrega (cerca de 2,5 vezes menos). Uma resposta do Fable foi reprovada de início por um erro do verificador, corrigido e reavaliado com `--reavaliar`. Relatório completo: [resultados/2026-11-19-2317-comprovantes](resultados/2026-11-19-2317-comprovantes/relatorio.md).

## Na prática: como o Nei escolhe

- **Luna e Haiku:** custam centavos e acertaram a tarefa simples. Boa opção para execução simples e longa (muitos passos repetidos, grande volume).
- **Terra e Sonnet:** nos testes do Nei, os preferidos são o GPT-6.1 Terra e o Claude Sonnet 5.5. Custam mais, mas entregam bom resultado com mais constância. Na OpenAI, do menor para o maior: Luna, Terra, Sol e Astra. O Terra não está nas tabelas deste projeto.
- **Neon como crítico:** hoje o Nei usa Claude e Codex um revisando o outro, porque modelos de empresas diferentes erram em pontos diferentes. O Gemini 4 Neon pode ser a IA que valida e critica para quem só tem o Claude ou só tem o Codex (como ligar: seção abaixo).

## Gemini Pro dentro do Claude Code ou do Codex

**O Gemini CLI venceu.** Em 18/06/2026 o Google parou de aceitar no Gemini CLI a conta de quem assina o Google AI Pro ou Ultra (e o uso grátis individual). O login dá: *"This client is no longer supported for Gemini Code Assist for individuals… migrate to the Antigravity suite"*. O substituto é o **Antigravity CLI (`agy`)**, que usa a cota da sua assinatura. A chave de API do AI Studio não usa a assinatura: tem cota própria, e no plano gratuito o Neon e o Argon dão 429.

**O processo que fizemos (19/11/2026):**

1. Chaves de API do Gemini que já existiam (plano gratuito): o Hydrogen respondeu; Neon e Argon, `429 You exceeded your current quota`.
2. Gemini CLI 0.70.0 com login na conta da assinatura: login aceito, uso recusado (mensagem acima).
3. Antigravity CLI 1.5.13: instalado, login pela conta Google (link → código colado de volta), `agy models` listou Gemini 4 Neon, Argon e Hydrogen (low a xhigh), Gemini 3.8 Flash, Claude Opus 5.5 e Sonnet 5.5.
4. O kit de testes ganhou a via `agy` e rodou os três Gemini pela assinatura.

**Como fazer:**

```bash
# 1. instalar (o script baixa o binário e confere o SHA-512)
curl -fsSL https://antigravity.google/cli/install.sh | bash      # instala em ~/.local/bin/agy

# 2. login: rode sem argumentos, escolha "Google OAuth", abra o link e entre com a conta que assina o Gemini
agy                                                                # depois cole o código de autorização

# 3. ver o que a sua conta libera
agy models

# 4. usar sem interação (é assim que o Claude Code, o Codex e o kit chamam)
agy -p "Critique este texto: ..." --model gemini-4-neon-high --output-format json
```

A saída JSON traz `response`, `duration_seconds` e `usage` (tokens de entrada, saída e raciocínio). Dentro do Claude Code ou do Codex, basta pedir à IA que chame o `agy` pelo terminal. Um uso bom é o Neon como segundo olhar: o Claude ou o Codex fazem, o Gemini critica.

No kit, `kit/motores.json` já aponta os três Gemini para a via `agy` (`gemini-4-neon-high`, `gemini-4-argon-high`, `gemini-4-hydrogen-high`).

**Cuidados:** a cota do Pro não tem número publicado (renova a cada 5 horas, com teto semanal); há relatos de contas Pro com "not eligible" no Antigravity; no esforço alto o Gemini pensa e escreve mais, o que encarece o "custo por uso" equivalente.

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

### Kit de testes

```bash
python3 kit/testar.py kit/exemplo-comprovantes --simular              # mostra o plano, não chama nada
python3 kit/testar.py kit/exemplo-comprovantes --so "Claude,GPT" --repeticoes 2
python3 kit/testar.py minha-tarefa/ --juiz claude-cli:claude-sonnet-5-5
python3 kit/testar.py kit/exemplo-comprovantes --reavaliar resultados/<pasta>   # refaz verificador e juiz nas respostas salvas
python3 kit/teste_vias_api.py                                         # testa as vias por API num servidor falso
```

**A tarefa** é uma pasta com `tarefa.json`:

```json
{"nome": "comprovantes",
 "pedido_arquivo": "pedido.md",
 "criterio": "como é 'ficou certo', ponto por ponto",
 "verificar": "python3 verificar.py",
 "repeticoes": 3}
```

`verificar` é opcional: um comando que recebe o caminho da resposta e sai com 0 quando ela está certa. A resposta só conta como certa se passar no verificador **e** no juiz.

**Os modelos** ficam em `kit/motores.json` (`modelo` igual ao nome em `dados/precos-*.csv`, `via`, `id`). Vias:

| Via | Como chama | Precisa de |
|---|---|---|
| `claude-cli` | `claude -p`, sem ferramentas | Claude Code logado (assinatura) |
| `codex-cli` | `codex exec`, sandbox só leitura | Codex logado (assinatura) |
| `agy` | `agy -p`, Antigravity CLI | Login com a conta Google que assina o Gemini (AI Pro/Ultra) |
| `gemini-cli` | `gemini -p` | Só com chave de API paga: a assinatura individual migrou para o `agy` |
| `api-anthropic`, `api-openai`, `api-google`, `openrouter` | API HTTP | `ANTHROPIC_API_KEY`, `OPENAI_API_KEY`, `GEMINI_API_KEY`, `OPENROUTER_API_KEY` |

O custo é calculado pelos tokens medidos × a tabela oficial. Claude Code, Codex e Gemini CLI acrescentam instruções próprias a cada pedido; o kit mede esse acréscimo uma vez por modelo e desconta (o número bruto fica na coluna `tokens_entrada_bruto`). Pela assinatura você não paga por tarefa: leia o custo como "quanto custaria por uso". Chamada que falha (cota, rede, login) aparece como "não rodou" e não conta como erro do modelo. As vias `claude-cli`, `codex-cli`, `agy` e `api-google` foram testadas de verdade; `api-anthropic`, `api-openai`, `openrouter` e `gemini-cli` só contra um servidor falso. Confira o `id` de cada modelo na documentação da empresa.

Saída em `resultados/<data>-<nome>/`: as respostas, `tentativas.csv` (que o `calcular.py` também lê) e `relatorio.md`.

### Arquivos

| Arquivo | O que é |
|---|---|
| `calcular.py` | Calcula o custo por entrega certa a partir de um CSV de tentativas |
| `dados/precos-2026-11-19.csv` | Preços oficiais por milhão de tokens, com a fonte de cada linha |
| `dados/arena-2026-11-19.csv` | Nota e custo mediano por tarefa no Agent Arena (recorte de 19/11/2026) |
| `exemplos/tentativas-exemplo.csv` | Exemplo **fictício** de teste (não é medição) |
| `kit/testar.py` | Kit de testes: roda a tarefa em cada IA, avalia e calcula o custo por entrega certa |
| `kit/motores.json` | Lista de modelos e como chamar cada um |
| `kit/exemplo-comprovantes/` | Tarefa de exemplo com verificador automático |
| `resultados/` | Relatórios dos testes já rodados |
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
