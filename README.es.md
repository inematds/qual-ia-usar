# ⚖️ Qué IA usar - GEMINI - GPT - CLAUDE

**🇧🇷 [Português](README.md) · 🇺🇸 [English](README.en.md) · 🇪🇸 [Español](README.es.md)**

[![Cuál IA resulta más barata](guia/assets/banner-es.jpg)](https://inematds.github.io/qual-ia-usar/guia/es/)

## Qué es

Este proyecto compara diez modelos de IA de tres empresas: Gemini 4 de Google (Neon, Argon y Hydrogen), Claude de Anthropic (Fable, Opus, Sonnet y Haiku) y los modelos de OpenAI que usa Codex (Astra, Sol y Luna). Reúne las tablas oficiales de precios y el puntaje de Agent Arena, un ranking público que mide el desempeño de agentes de IA en tareas reales, consultados el 19/11/2026. Sirve para quienes pagan por IA y quieren elegir sin desperdiciar dinero. Para leerlo, no hace falta nada; para probarlo con tu propia tarea, basta con Claude Code o Codex.

## 📖 Guía

Guía completa, en lenguaje sencillo: **https://inematds.github.io/qual-ia-usar/guia/es/**

## La idea en una línea

La IA más barata en la tabla puede salir más cara en tu factura. Lo que importa es el **costo por entrega correcta**: todo lo que pagaste, incluidos los intentos fallidos, dividido entre las tareas que quedaron bien.

## Quién gana en cada rango (19/11/2026)

Precio en US$ por millón de tokens (entrada / salida). Puntaje y costo por tarea: Agent Arena.

| Rango | Google | Anthropic | OpenAI |
|---|---|---|---|
| Trabajo complejo | Gemini 4 Neon · 3 / 15 · puntaje 1333 · US$ 2,60 por tarea | Claude Opus 5.5 · 4 / 20 · 1336 · US$ 5,98 | GPT-6.2 Astra · 8 / 40 · 1291 · US$ 3,11 |
| Día a día | Gemini 4 Argon · 2 / 10 (4 / 20 a partir del 1/12) · 1229 · US$ 0,66 | Claude Sonnet 5.5 · 2 / 10 · 1296 · US$ 3,27 | GPT-6.2 Sol · 2 / 10 · 1241 · US$ 0,96 |
| Gran volumen | Gemini 4 Hydrogen · 1,50 / 7,50 · 1271 (preliminar) · US$ 1,50 | Claude Haiku 5.5 · 0,10 / 0,50 · sin puntaje | GPT-6 Luna · 0,10 / 0,50 · sin puntaje |

Fuera de estos rangos: **Claude Fable 5.2** (US$ 8 / 40) lidera el ranking con un puntaje de 1448 y cuesta US$ 9,16 por tarea.

- **Complejo:** Neon casi empata con Opus y cuesta menos de la mitad por tarea.
- **Día a día:** los tres cobran lo mismo por token; por tarea, Argon resulta más barato y Sonnet tiene el mejor puntaje.
- **Volumen:** Haiku y Luna cobran 15 veces menos por token que Hydrogen; su calidad solo se descubre al probarlos.
- **Dentro de Google:** Hydrogen es más barato por token que Argon, pero costó más del doble por tarea.

Lo que esta comparación no promete: las cifras son las publicadas (todavía no se hicieron pruebas propias con los diez modelos), el ranking mide tareas de agentes en general y no las tuyas, y todo cambia con el tiempo.

## Cómo empezar (sin programar)

Abre Claude Code o Codex en una carpeta tuya y pega:

```text
Lee el proyecto "Qual IA usar" en https://github.com/inematds/qual-ia-usar (el README explica el método y la calculadora).
Quiero saber qué IA resulta más barata por entrega correcta en una tarea mía: [describe la tarea y qué significa que "quedó bien"].
1. Dime, en lenguaje sencillo, qué 3 o 4 modelos vale la pena probar para esa tarea y por qué.
2. Propón una prueba pequeña: cuántas veces ejecutar cada modelo y cuánto debería costar.
3. No llames a ningún modelo ni gastes nada antes de que te diga que sí.
Después de que te diga que sí, registra cada intento en el formato del proyecto, ejecuta la calculadora y muéstrame el resultado.
```

---

## Instalación técnica

Solo necesitas Python 3 (ninguna biblioteca adicional).

```bash
git clone https://github.com/inematds/qual-ia-usar
cd qual-ia-usar
python3 calcular.py --precos                              # tabla de precios por token
python3 calcular.py --arena                               # ranking de Agent Arena + puntos por dólar
python3 calcular.py exemplos/tentativas-exemplo.csv       # ejemplo ficticio de prueba
```

### Archivos

| Archivo | Qué es |
|---|---|
| `calcular.py` | Calcula el costo por entrega correcta a partir de un CSV de intentos |
| `dados/precos-2026-11-19.csv` | Precios oficiales por millón de tokens, con la fuente de cada fila |
| `dados/arena-2026-11-19.csv` | Puntaje y costo mediano por tarea en Agent Arena (datos del 19/11/2026) |
| `exemplos/tentativas-exemplo.csv` | Ejemplo **ficticio** de prueba (no es una medición) |
| `guia/` | La guía en PT, EN y ES (GitHub Pages) |

### Formato del CSV de intentos

Una fila por intento:

| Columna | Qué va |
|---|---|
| `modelo` | Igual al nombre en `dados/precos-2026-11-19.csv` (p. ej., `Gemini 4 Argon`) |
| `execucao` | Etiqueta de cada vez que diste la tarea desde cero (1, 2, 3…). Las correcciones de una misma ejecución suman el costo y cuentan como una entrega |
| `tokens_entrada`, `tokens_saida` | Tokens consumidos en el intento |
| `custo_usd` | Importe cobrado, si el panel lo muestra. Vacío = se calcula con los tokens y la tabla |
| `aprovada` | `sim` o `não`. La ejecución cuenta como entrega si se aprobó alguno de sus intentos |

Si falta el costo, nunca se considera cero: el modelo aparece como "sin costo" y queda fuera de la comparación.

### Cómo se hace el cálculo

`costo por entrega correcta = suma del costo de todos los intentos ÷ número de ejecuciones aprobadas`

Para probar con tareas preparadas y datos ficticios, usa el protocolo del laboratorio de Gemini 4: [protocolo.md](https://github.com/inematds/gemini-4-na-pratica/blob/main/laboratorio/protocolo.md).

## Fuentes

- Google: [precios](https://aistudio.google.com/docs/pricing) · [Neon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) · [Argon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-argon/) · [Hydrogen](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/)
- Anthropic: [precios](https://platform.claude.com/docs/en/about-claude/pricing) · [Haiku 5.5](https://www.anthropic.com/claude-haiku-5-5)
- OpenAI: [precios](https://developers.openai.com/api/docs/pricing) · [GPT-6.2](https://openai.com/index/introducing-gpt-6-2-astra-sol/) · [GPT-6 Luna](https://developers.openai.com/api/docs/models/gpt-6-luna)
- [Agent Arena](https://arena.ai/leaderboard/agent): Google con esfuerzo High, Anthropic y OpenAI en Max; costo = mediana por tarea de los últimos 14 días; el puntaje no es un porcentaje de aciertos.

## El proceso, de principio a fin

| # | Paso | Comando | Quién |
|---|---|---|---|
| 1 | Revisar precios y ranking en las fuentes oficiales y actualizar `dados/*.csv` | — | 🧠 sesión con Nei |
| 2 | Revisar las tablas y el cálculo | `python3 calcular.py --precos` / `--arena` / `exemplos/tentativas-exemplo.csv` | ⚙️ script |
| 3 | Escribir la guía PT (`guia/index.html`) y generar la portada y los banners | `gerar-capa.cjs`, `gerar-banner.sh` | 🧠 + ⚙️ Codex image_gen |
| 4 | Traducir la guía y el README a EN/ES | `traduz-pagina-codex.py html` / `readme` | ⚙️ traductor central |
| 5 | Revisión independiente de la guía | `revisor-nota.py registra --fluxo guia` | 🤖 nuevo revisor |
| 6 | Publicar: commit + push (GitHub Pages mediante Actions) | `git push` | 🧠 |
| 7 | Portal, búsqueda y catálogo PRO | skill `atualiza-portal` | 🧠 |
| 8 | Tema en INEMA.LLMS | skill `postar-telegram` | 🧠 |
| 9 | Video de la comparación en lives4 e inserción en la guía (3 idiomas) | `yt-pub-x3` | ⚙️ x3 + 🧠 |

Gratis en inema.club, directamente en internet. Licencia MIT.
