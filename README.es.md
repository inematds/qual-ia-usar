# ⚖️ Qué IA usar - GEMINI - GPT - CLAUDE

**🇧🇷 [Português](README.md) · 🇺🇸 [English](README.en.md) · 🇪🇸 [Español](README.es.md)**

[![Cuál IA cuesta menos](guia/assets/banner.jpg)](https://inematds.github.io/qual-ia-usar/guia/es/)

## Qué es

Este proyecto compara diez modelos de IA de tres empresas: Gemini 4 de Google (Neon, Argon y Hydrogen), Claude de Anthropic (Fable, Opus, Sonnet y Haiku) y los modelos de OpenAI que usa Codex (Astra, Sol y Luna). Reúne las tablas oficiales de precios y la clasificación de Agent Arena, un ranking público que mide agentes de IA realizando tareas reales, consultados el 19/11/2026. Está pensado para quienes pagan por IA y quieren elegir sin desperdiciar dinero. Para leerlo, no necesitas nada; para probarlo con una tarea propia, basta con Claude Code o Codex.

## 📖 Guía

Guía completa, en lenguaje sencillo: **https://inematds.github.io/qual-ia-usar/guia/es/**

## La idea en una línea

La IA más barata en la tabla puede salir más cara en tu factura. Lo que importa es el **costo por entrega correcta**: todo lo que pagaste, incluidos los intentos fallidos, dividido entre las tareas que quedaron correctas.

## Quién gana en cada categoría (19/11/2026)

Precio en US$ por millón de tokens (entrada / salida). Puntuación y costo por tarea: Agent Arena.

| Categoría | Google | Anthropic | OpenAI |
|---|---|---|---|
| Trabajo complejo | Gemini 4 Neon · 3 / 15 · puntuación 1333 · US$ 2,60 por tarea | Claude Opus 5.5 · 4 / 20 · 1336 · US$ 5,98 | GPT-6.2 Astra · 8 / 40 · 1291 · US$ 3,11 |
| Día a día | Gemini 4 Argon · 2 / 10 (4 / 20 a partir del 1/12) · 1229 · US$ 0,66 | Claude Sonnet 5.5 · 2 / 10 · 1296 · US$ 3,27 | GPT-6.2 Sol · 2 / 10 · 1241 · US$ 0,96 |
| Gran volumen | Gemini 4 Hydrogen · 1,50 / 7,50 · 1271 (preliminar) · US$ 1,50 | Claude Haiku 5.5 · 0,10 / 0,50 · sin puntuación | GPT-6 Luna · 0,10 / 0,50 · sin puntuación |

Fuera de las categorías: **Claude Fable 5.2** (US$ 8 / 40) lidera la clasificación con una puntuación de 1448 y cuesta US$ 9,16 por tarea.

- **Complejo:** Neon casi empata con Opus y cuesta menos de la mitad por tarea.
- **Día a día:** los tres cobran lo mismo por token; por tarea, Argon cuesta menos y Sonnet tiene la mejor puntuación.
- **Volumen:** Haiku y Luna cobran 15 veces menos por token que Hydrogen; su calidad solo se descubre probándolos.
- **Dentro de Google:** Hydrogen es más barato por token que Argon, pero costó más del doble por tarea.

Lo que esta comparación no promete: las cifras de las categorías son las publicadas (la prueba propia, más abajo, cubre una tarea y siete modelos), la clasificación mide tareas generales de agentes y no la tuya, y todo cambia con el tiempo.

## Cómo empezar (sin programar)

Abre Claude Code o Codex en una carpeta tuya y pega:

```text
Lee el proyecto "Qual IA usar" en https://github.com/inematds/qual-ia-usar (el README explica el método y la calculadora).
Quiero saber qué IA cuesta menos por entrega correcta para una tarea mía: [describe la tarea y qué significa que "quedó correcta"].
1. Dime, en español sencillo, qué 3 o 4 modelos vale la pena probar para esa tarea y por qué.
2. Propón una prueba pequeña: cuántas veces ejecutar cada modelo y cuánto debería costar.
3. No llames a ningún modelo ni gastes nada antes de que te diga que sí.
Después de que te diga que sí, prepara la tarea en el formato del kit (kit/testar.py), ejecuta la prueba y muéstrame el informe.
```

## Kit de pruebas: tu tarea en todas las IA

Describes la tarea y qué significa que "quedó correcta". El kit ejecuta la misma tarea varias veces en cada IA, evalúa cada respuesta (con un juez de IA y, si quieres, un verificador automático) y entrega un informe: cuántas quedaron correctas, tiempo y costo por entrega correcta.

**Prueba real (19/11/2026, tarea de los comprobantes, 2 veces cada uno, con la suscripción):**

| Modelo | Correctas | US$ por entrega correcta | Tiempo mediano |
|---|---:|---:|---:|
| GPT-6 Luna | 2/2 | 0,0001 | 7 s |
| Claude Haiku 5.5 | 2/2 | 0,0004 | 6 s |
| GPT-6.2 Sol | 2/2 | 0,0014 | 9 s |
| Claude Sonnet 5.5 | 2/2 | 0,0031 | 4 s |
| GPT-6.2 Astra | 2/2 | 0,0064 | 10 s |
| Claude Opus 5.5 | 2/2 | 0,0086 | 7 s |
| Claude Fable 5.2 | 2/2 | 0,0181 | 5 s |

En una tarea sencilla todos aciertan, y entonces gana el más barato: Fable costó unas 270 veces más que Luna por la misma entrega. Los tres Gemini quedaron fuera de esta prueba (Gemini CLI no estaba instalado). Informe completo: [resultados/2026-11-19-2150-comprovantes](resultados/2026-11-19-2150-comprovantes/relatorio.md).

---

## Instalación técnica

Solo necesitas Python 3 (ninguna biblioteca adicional).

```bash
git clone https://github.com/inematds/qual-ia-usar
cd qual-ia-usar
python3 calcular.py --precos                              # tabla de precios por token
python3 calcular.py --arena                               # clasificación de Agent Arena + puntos por dólar
python3 calcular.py ejemplos/tentativas-exemplo.csv       # ejemplo ficticio de prueba
```

### Kit de pruebas

```bash
python3 kit/testar.py kit/exemplo-comprovantes --simular              # muestra el plan, no llama a nada
python3 kit/testar.py kit/exemplo-comprovantes --so "Claude,GPT" --repeticoes 2
python3 kit/testar.py minha-tarefa/ --juiz claude-cli:claude-sonnet-5-5
python3 kit/teste_vias_api.py                                         # prueba las vías de API en un servidor falso
```

**La tarea** es una carpeta con `tarefa.json`:

```json
{"nome": "comprovantes",
 "pedido_arquivo": "pedido.md",
 "criterio": "cómo es 'quedó correcta', punto por punto",
 "verificar": "python3 verificar.py",
 "repeticoes": 3}
```

`verificar` es opcional: un comando que recibe la ruta de la respuesta y termina con 0 cuando es correcta. La respuesta solo cuenta como correcta si pasa el verificador **y** el juez.

**Los modelos** están en `kit/motores.json` (`modelo` igual al nombre en `dados/precos-*.csv`, `via`, `id`). Vías:

| Vía | Cómo se llama | Necesita |
|---|---|---|
| `claude-cli` | `claude -p`, sin herramientas | Claude Code con sesión iniciada (suscripción) |
| `codex-cli` | `codex exec`, sandbox de solo lectura | Codex con sesión iniciada (suscripción) |
| `gemini-cli` | `gemini -p` | Gemini CLI instalado y con sesión iniciada |
| `api-anthropic`, `api-openai`, `api-google`, `openrouter` | API HTTP | `ANTHROPIC_API_KEY`, `OPENAI_API_KEY`, `GEMINI_API_KEY`, `OPENROUTER_API_KEY` |

El costo se calcula con los tokens medidos × la tabla oficial. Claude Code, Codex y Gemini CLI agregan instrucciones propias a cada solicitud; el kit mide ese incremento una vez por modelo y lo descuenta (el número bruto queda en la columna `tokens_entrada_bruto`). Con la suscripción no pagas por tarea: interpreta el costo como «cuánto costaría por uso». Las vías de API y la vía `gemini-cli` solo se probaron contra un servidor falso; verifica el `id` de cada modelo en la documentación de la empresa.

Salida en `resultados/<data>-<nombre>/`: las respuestas, `tentativas.csv` (que `calcular.py` también lee) y `relatorio.md`.

### Archivos

| Archivo | Qué es |
|---|---|
| `calcular.py` | Calcula el costo por entrega correcta a partir de un CSV de intentos |
| `dados/precos-2026-11-19.csv` | Precios oficiales por millón de tokens, con la fuente de cada línea |
| `dados/arena-2026-11-19.csv` | Puntuación y costo mediano por tarea en Agent Arena (corte del 19/11/2026) |
| `exemplos/tentativas-exemplo.csv` | Ejemplo **ficticio** de prueba (no es una medición) |
| `kit/testar.py` | Kit de pruebas: ejecuta la tarea en cada IA, evalúa y calcula el costo por entrega correcta |
| `kit/motores.json` | Lista de modelos y cómo llamar a cada uno |
| `kit/exemplo-comprovantes/` | Tarea de ejemplo con verificador automático |
| `resultados/` | Informes de las pruebas ya ejecutadas |
| `guia/` | La guía en PT, EN y ES (GitHub Pages) |

### Formato del CSV de intentos

Una línea por intento:

| Columna | Qué contiene |
|---|---|
| `modelo` | Igual al nombre en `dados/precos-2026-11-19.csv` (ej.: `Gemini 4 Argon`) |
| `execucao` | Etiqueta de cada vez que diste la tarea desde cero (1, 2, 3…). Las correcciones de una misma ejecución suman costo y cuentan como una entrega |
| `tokens_entrada`, `tokens_saida` | Tokens consumidos en el intento |
| `custo_usd` | Importe cobrado, si el panel lo muestra. Vacío = se calcula con los tokens y la tabla |
| `aprovada` | `sim` o `não`. La ejecución cuenta como entrega si se aprobó alguno de sus intentos |

Un costo ausente nunca se convierte en cero: el modelo aparece como «sin costo» y queda fuera de la comparación.

### Cómo se calcula

`costo por entrega correcta = suma del costo de todos los intentos ÷ número de ejecuciones aprobadas`

Para probar con tareas listas y datos ficticios, usa el protocolo del laboratorio de Gemini 4: [protocolo.md](https://github.com/inematds/gemini-4-na-pratica/blob/main/laboratorio/protocolo.md).

## Fuentes

- Google: [precios](https://aistudio.google.com/docs/pricing) · [Neon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) · [Argon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-argon/) · [Hydrogen](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/)
- Anthropic: [precios](https://platform.claude.com/docs/en/about-claude/pricing) · [Haiku 5.5](https://www.anthropic.com/claude-haiku-5-5)
- OpenAI: [precios](https://developers.openai.com/api/docs/pricing) · [GPT-6.2](https://openai.com/index/introducing-gpt-6-2-astra-sol/) · [GPT-6 Luna](https://developers.openai.com/api/docs/models/gpt-6-luna)
- [Agent Arena](https://arena.ai/leaderboard/agent): Google en esfuerzo High, Anthropic y OpenAI en Max; costo = mediana por tarea de los últimos 14 días; la puntuación no es un porcentaje de aciertos.

## El proceso, de principio a fin

| # | Paso | Comando | Quién |
|---|---|---|---|
| 1 | Verificar precios y clasificación en las fuentes oficiales y actualizar `dados/*.csv` | — | 🧠 sesión con Nei |
| 2 | Verificar las tablas y el cálculo | `python3 calcular.py --precos` / `--arena` / `exemplos/tentativas-exemplo.csv` | ⚙️ script |
| 3 | Escribir la guía PT (`guia/index.html`) y generar portada y banners | `gerar-capa.cjs`, `gerar-banner.sh` | 🧠 + ⚙️ Codex image_gen |
| 4 | Traducir la guía y el README a EN/ES | `traduz-pagina-codex.py html` / `readme` | ⚙️ traductor central |
| 5 | Revisión independiente de la guía | `revisor-nota.py registra --fluxo guia` | 🤖 revisor nuevo |
| 6 | Publicar: commit + push (GitHub Pages vía Actions) | `git push` | 🧠 |
| 7 | Portal, búsqueda y catálogo PRO | skill `atualiza-portal` | 🧠 |
| 8 | Publicar un tema en INEMA.LLMS | skill `postar-telegram` | 🧠 |
| 9 | Video de la comparación en lives4 e inserción en la guía (3 idiomas) | `yt-pub-x3` | ⚙️ x3 + 🧠 |

Gratis en inema.club, directamente en internet. Licencia MIT.
