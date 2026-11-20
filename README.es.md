# ⚖️ Qué IA usar - GEMINI - GPT - CLAUDE

**🇧🇷 [Português](README.md) · 🇺🇸 [English](README.en.md) · 🇪🇸 [Español](README.es.md)**

[![Qué IA cuesta menos](guia/assets/banner-es.jpg)](https://inematds.github.io/qual-ia-usar/guia/es/)

## Qué es

Este proyecto compara diez modelos de IA de tres empresas: Gemini 4 de Google (Neon, Argon y Hydrogen), Claude de Anthropic (Fable, Opus, Sonnet y Haiku) y los modelos de OpenAI que usa Codex (Astra, Sol y Luna). Reúne las tablas oficiales de precios y el marcador de Agent Arena, un marcador público que mide agentes de IA que realizan tareas reales, versión consultada el 19/11/2026. Está pensado para quienes pagan por IA y quieren elegir sin desperdiciar dinero. Para leerlo, no necesitas nada. Para probarlo con tu propia tarea, basta con las aplicaciones que ya usas (ChatGPT, Claude o Gemini), o con el kit de pruebas, que ejecuta la misma tarea en todas las IA que actives y te dice cuál acertó más y gastó menos.

## 📖 Guía

Guía completa, en lenguaje sencillo: **https://inematds.github.io/qual-ia-usar/guia/es/**

## La idea en una línea

La IA más barata de la tabla puede salir más cara en tu factura. Lo que importa es el **costo por entrega correcta**: todo lo que pagaste, incluidos los intentos fallidos, dividido entre las tareas que quedaron correctas.

## Quién gana en cada rango (19/11/2026)

Precio en US$ por millón de tokens (entrada / salida). Puntuación y costo por tarea: Agent Arena.

| Rango | Google | Anthropic | OpenAI |
|---|---|---|---|
| Trabajo complejo | Gemini 4 Neon · 3 / 15 · Puntuación 1333 · US$ 2,60 por tarea | Claude Opus 5.5 · 4 / 20 · 1336 · US$ 5,98 | GPT-6.2 Astra · 8 / 40 · 1291 · US$ 3,11 |
| Día a día | Gemini 4 Argon · 2 / 10 (4 / 20 a partir del 1 de diciembre) · 1229 · US$ 0,66 | Claude Sonnet 5.5 · 2 / 10 · 1296 · US$ 3,27 | GPT-6.2 Sol · 2 / 10 · 1241 · US$ 0,96 |
| Gran volumen | Gemini 4 Hydrogen · 1,50 / 7,50 · 1271 (preliminar) · US$ 1,50 | Claude Haiku 5.5 · 0,10 / 0,50 · sin puntuación | GPT-6 Luna · 0,10 / 0,50 · sin puntuación |

Fuera de los rangos: **Claude Fable 5.2** (US$ 8 / 40) lidera el marcador con una puntuación de 1448 y cuesta US$ 9,16 por tarea.

- **Complejo:** Neon casi empata con Opus y cuesta menos de la mitad por tarea.
- **Día a día:** los tres cobran lo mismo por token; por tarea, Argon cuesta menos y Sonnet tiene la mejor puntuación.
- **Volumen:** Haiku y Luna cobran 15 veces menos por token que Hydrogen; su calidad solo se descubre probándolos.
- **Dentro de Google:** Hydrogen es más barato por token que Argon, pero costó más del doble por tarea.

Lo que esta comparación no promete: las cifras de los rangos son las publicadas (la prueba propia, más abajo, cubre una tarea y siete modelos), el marcador mide tareas de agentes en general, no la tuya, y todo cambia con el tiempo.

## Todas las comparaciones (resumen)

Cuatro comparaciones entre Google, Anthropic y OpenAI, del 19 y 20/11/2026. Solo las cifras.

| Comparación | Qué se midió | Google (Gemini 4) | Anthropic (Claude) | OpenAI (GPT) |
|---|---|---|---|---|
| **1. Precio oficial** (10 modelos) | US$ por millón de tokens, entrada / salida | Neon 3 / 15 · Argon 2 / 10 · Hydrogen 1,50 / 7,50 | Fable 8 / 40 · Opus 4 / 20 · Sonnet 2 / 10 · Haiku 0,10 / 0,50 | Astra 8 / 40 · Sol 2 / 10 · Luna 0,10 / 0,50 |
| **2. Marcador de Agent Arena** (8 con puntuación) | puntuación · US$ por tarea | Neon 1333 · 2,60 · Hydrogen 1271 · 1,50 · Argon 1229 · 0,66 | Fable 1448 · 9,16 · Opus 1336 · 5,98 · Sonnet 1296 · 3,27 | Astra 1291 · 3,11 · Sol 1241 · 0,96 |
| **3. Kit de pruebas** (comprobantes, 10 × 2, con suscripción) | aciertos · ¢ por entrega correcta · tiempo | 3 de 3 · 1,92–3,62 ¢ · 12–16 s (esfuerzo alto) | 4 de 4 · 0,038–1,55 ¢ · 4–6 s | 3 de 3 · 0,008–0,66 ¢ · 7–11 s |
| **4. Análisis de un documento largo** (182 KB, mismo pedido, contenido interno no publicado) | tiempo · recuentos incorrectos · puntuación de calidad (nuestra) | Neon: 5,5 min · 3 · 6,5 | Fable 5.2: 14 min · 0 · 9 | Astra: 4,5 min · 0 · 8 |

- **Calidad:** en el análisis largo, Fable fue el más riguroso y Astra ofreció la mejor relación costo-beneficio. Neon fue el más exhaustivo, pero se equivocó en los recuentos y llegó a conclusiones que los otros dos refutaron.
- **Costo:** en la tarea sencilla todos acertaron y GPT-6 Luna fue el más barato. Con esfuerzo alto, Gemini piensa más y resultó el más caro por entrega.
- **Velocidad:** Claude Sonnet fue el más rápido en la tarea sencilla (4 s), y Astra en el análisis largo (4,5 min); Fable tardó tres veces más.
- La puntuación de calidad del análisis es una evaluación nuestra: Astra y Fable comprobaron las cifras de Neon con el documento y llegaron a las mismas correcciones. Neon respondió primero, y los otros dos leyeron su análisis. Una tarea y un documento no bastan para decir qué modelo es mejor en general.

## Cómo empezar (sin programar)

Abre Claude Code o Codex en una carpeta tuya y pega:

```text
Lee el proyecto "Qué IA usar" en https://github.com/inematds/qual-ia-usar (el README explica el kit de pruebas en kit/testar.py).
Quiero saber qué IA cuesta menos por entrega correcta en una tarea mía: [describe la tarea y cómo se determina que "quedó correcta"].
1. Dime, en español sencillo, qué 3 o 4 modelos vale la pena probar para esa tarea y por qué.
2. Propón una prueba pequeña: cuántas veces ejecutar cada modelo y cuánto debería costar.
3. No llames a ningún modelo ni gastes nada antes de que te diga que sí.
Después de que te diga que sí, prepara la tarea en el formato del kit (kit/testar.py), ejecuta la prueba y muéstrame el informe.
```

## Kit de pruebas: tu tarea en todas las IA

Describe la tarea y cómo se determina que "quedó correcta". El kit ejecuta la misma tarea varias veces en cada IA, evalúa cada respuesta (un juez de IA y, si quieres, un verificador automático) y genera un informe: cuántas quedaron correctas, el tiempo y el costo por entrega correcta.

**Prueba real (19/11/2026, tarea de los comprobantes, 2 veces cada uno, todos con suscripción: Claude mediante Claude Code, GPT mediante Codex, Gemini mediante Google AI Pro a través de Antigravity CLI):**

| Modelo | Correctas | US$ por entrega correcta | Tiempo mediano |
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

En una tarea sencilla todos aciertan, así que gana el más barato. Los tres Gemini se ejecutaron con esfuerzo **high** (el mismo del marcador) y piensan bastante antes de responder (de 1.600 a 2.900 tokens de salida); Claude y GPT se ejecutaron con el esfuerzo predeterminado de cada asistente. Por la API, con el esfuerzo predeterminado, Hydrogen costó US$ 0,0087 por entrega (unas 2,5 veces menos). Al principio se rechazó una respuesta de Fable por un error del verificador, que se corrigió y volvió a evaluar con `--reavaliar`. Informe completo: [resultados/2026-11-19-2317-comprovantes](resultados/2026-11-19-2317-comprovantes/relatorio.md) (en portugués).

## En la práctica: cómo elige Nei

- **Luna y Haiku:** cuestan centavos y acertaron la tarea sencilla. Son una buena opción para trabajos sencillos y largos (muchos pasos repetidos, gran volumen).
- **Terra y Sonnet:** en las pruebas de Nei, sus preferidos son GPT-6.1 Terra y Claude Sonnet 5.5. Cuestan más, pero dan buenos resultados con mayor constancia. En OpenAI, del menor al mayor: Luna, Terra, Sol y Astra. Terra no está en las tablas de este proyecto.
- **Neon como crítico:** hoy Nei usa Claude y Codex para que uno revise al otro, porque los modelos de distintas empresas se equivocan en aspectos diferentes. Gemini 4 Neon puede ser la IA que valida y critica si solo tienes Claude o Codex (cómo conectarlo: en la sección de abajo).

## Gemini Pro dentro de Claude Code o Codex

**Gemini CLI fue retirado.** El 18/06/2026, Google dejó de aceptar en Gemini CLI las cuentas con suscripción a Google AI Pro o Ultra (y el uso individual gratuito). Al iniciar sesión aparece: *"This client is no longer supported for Gemini Code Assist for individuals… migrate to the Antigravity suite"*. El reemplazo es **Antigravity CLI (`agy`)**, que usa la cuota de tu suscripción. La clave de API de AI Studio no usa la suscripción: tiene su propia cuota, y en el plan gratuito Neon y Argon responden con 429.

**El proceso que seguimos (19/11/2026):**

1. Claves de API de Gemini que ya existían (plan gratuito): Hydrogen respondió; Neon y Argon, `429 You exceeded your current quota`.
2. Gemini CLI 0.70.0 con inicio de sesión en la cuenta de la suscripción: inicio de sesión aceptado, uso rechazado (mensaje anterior).
3. Antigravity CLI 1.5.13: instalado; inicio de sesión con la cuenta de Google (enlace → código pegado de vuelta); `agy models` mostró Gemini 4 Neon, Argon y Hydrogen (de low a xhigh), Gemini 3.8 Flash, Claude Opus 5.5 y Sonnet 5.5.
4. El kit de pruebas incorporó la vía `agy` y ejecutó los tres Gemini con la suscripción.

**Cómo hacerlo:**

```bash
# 1. instalar (el script descarga el binario y verifica el SHA-512)
curl -fsSL https://antigravity.google/cli/install.sh | bash      # instala en ~/.local/bin/agy

# 2. iniciar sesión: ejecuta sin argumentos, elige "Google OAuth", abre el enlace e inicia sesión con la cuenta que tiene la suscripción a Gemini
agy                                                                # luego pega el código de autorización

# 3. ver qué permite tu cuenta
agy models

# 4. usar sin interacción (así lo llaman Claude Code, Codex y el kit)
agy -p "Critique este texto: ..." --model gemini-4-neon-high --output-format json
```

La salida JSON incluye `response`, `duration_seconds` y `usage` (tokens de entrada, salida y razonamiento). Dentro de Claude Code o Codex, basta con pedirle a la IA que llame a `agy` desde la terminal. Un buen uso es Neon como segunda opinión: Claude o Codex hacen el trabajo y Gemini lo critica.

En el kit, `kit/motores.json` ya apunta los tres Gemini a la vía `agy` (`gemini-4-neon-high`, `gemini-4-argon-high`, `gemini-4-hydrogen-high`).

**Precauciones:** la cuota de Pro no tiene una cifra publicada (se renueva cada 5 horas, con un límite semanal); hay informes de cuentas Pro que aparecen como "not eligible" en Antigravity; con esfuerzo alto, Gemini piensa y escribe más, lo que encarece el equivalente al "costo por uso".

---

## Instalación técnica

Solo necesitas Python 3 (ninguna biblioteca adicional).

```bash
git clone https://github.com/inematds/qual-ia-usar
cd qual-ia-usar
python3 calcular.py --precos                              # tabla de precios por token
python3 calcular.py --arena                               # marcador de Agent Arena + puntos por dólar
python3 calcular.py exemplos/tentativas-exemplo.csv       # ejemplo ficticio de prueba
```

### Kit de pruebas

```bash
python3 kit/testar.py kit/exemplo-comprovantes --simular              # muestra el plan, no llama a nada
python3 kit/testar.py kit/exemplo-comprovantes --so "Claude,GPT" --repeticoes 2
python3 kit/testar.py minha-tarefa/ --juiz claude-cli:claude-sonnet-5-5
python3 kit/testar.py kit/exemplo-comprovantes --reavaliar resultados/<pasta>   # vuelve a ejecutar el verificador y el juez con las respuestas guardadas
python3 kit/teste_vias_api.py                                         # prueba las vías de API en un servidor falso
```

**La tarea** es una carpeta con `tarefa.json`:

```json
{"nome": "comprovantes",
 "pedido_arquivo": "pedido.md",
 "criterio": "como é 'ficou certo', ponto por ponto",
 "verificar": "python3 verificar.py",
 "repeticoes": 3}
```

`verificar` es opcional: un comando que recibe la ruta de la respuesta y termina con 0 cuando esta es correcta. La respuesta solo cuenta como correcta si pasa el verificador **y** el juez.

**Los modelos** están en `kit/motores.json` (`modelo` igual al nombre en `dados/precos-*.csv`, `via`, `id`). Vías:

| Vía | Cómo se llama | Necesita |
|---|---|---|
| `claude-cli` | `claude -p`, sin herramientas | Claude Code con sesión iniciada (suscripción) |
| `codex-cli` | `codex exec`, solo lectura en sandbox | Codex con sesión iniciada (suscripción) |
| `agy` | `agy -p`, Antigravity CLI | Inicio de sesión con la cuenta de Google que tiene la suscripción a Gemini (AI Pro/Ultra) |
| `gemini-cli` | `gemini -p` | Solo con clave de API paga: la suscripción individual migró a `agy` |
| `api-anthropic`, `api-openai`, `api-google`, `openrouter` | API HTTP | `ANTHROPIC_API_KEY`, `OPENAI_API_KEY`, `GEMINI_API_KEY`, `OPENROUTER_API_KEY` |

El costo se calcula con los tokens medidos × la tabla oficial. Claude Code, Codex y Gemini CLI agregan instrucciones propias a cada pedido; el kit mide ese aumento una vez por modelo y lo descuenta (la cifra bruta queda en la columna `tokens_entrada_bruto`). Con la suscripción no pagas por tarea: interpreta el costo como «cuánto costaría por uso». Las llamadas que fallan (cuota, red, inicio de sesión) aparecen como «no se ejecutó» y no cuentan como errores del modelo. Se probaron de verdad las vías `claude-cli`, `codex-cli`, `agy` y `api-google`; `api-anthropic`, `api-openai`, `openrouter` y `gemini-cli` solo se probaron contra un servidor falso. Verifica el `id` de cada modelo en la documentación de la empresa.

Salida en `resultados/<data>-<nombre>/`: las respuestas, `tentativas.csv` (que también lee `calcular.py`) y `relatorio.md`.

### Archivos

| Archivo | Qué es |
|---|---|
| `calcular.py` | Calcula el costo por entrega correcta a partir de un CSV de intentos |
| `dados/precos-2026-11-19.csv` (en portugués) | Precios oficiales por millón de tokens, con la fuente de cada fila |
| `dados/arena-2026-11-19.csv` (en portugués) | Puntuación y costo mediano por tarea en Agent Arena (corte del 19/11/2026) |
| `exemplos/tentativas-exemplo.csv` (en portugués) | Ejemplo **ficticio** de prueba (no es una medición) |
| `kit/testar.py` | Kit de pruebas: ejecuta la tarea en cada IA, evalúa y calcula el costo por entrega correcta |
| `kit/motores.json` | Lista de modelos y cómo llamar a cada uno |
| `kit/exemplo-comprovantes/` (en portugués) | Tarea de ejemplo con verificador automático |
| `resultados/` (en portugués) | Informes de pruebas ya ejecutadas |
| `guia/` | La guía en PT, EN y ES (GitHub Pages) |

### Formato del CSV de intentos

Una fila por intento:

| Columna | Qué contiene |
|---|---|
| `modelo` | Igual al nombre en `dados/precos-2026-11-19.csv` (por ejemplo, `Gemini 4 Argon`) |
| `execucao` | Etiqueta de cada vez que diste la tarea desde cero (1, 2, 3…). Las correcciones de una misma ejecución suman el costo y cuentan como una entrega |
| `tokens_entrada`, `tokens_saida` | Tokens gastados en el intento |
| `custo_usd` | Importe cobrado, si el panel lo muestra. Vacío = se calcula con los tokens y la tabla |
| `aprovada` | `sim` o `não`. La ejecución cuenta como entrega si se aprobó alguno de sus intentos |

La falta de costo nunca se convierte en cero: el modelo aparece como «sin costo» y queda fuera de la comparación.

### Cómo se calcula

`costo por entrega correcta = suma del costo de todos los intentos ÷ número de ejecuciones aprobadas`

Para probar con tareas preparadas y datos ficticios, usa el protocolo del laboratorio de Gemini 4: [protocolo.md](https://github.com/inematds/gemini-4-na-pratica/blob/main/laboratorio/protocolo.md).

## Fuentes

- Google: [precios](https://aistudio.google.com/docs/pricing) · [Neon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) · [Argon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-argon/) · [Hydrogen](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/)
- Anthropic: [precios](https://platform.claude.com/docs/en/about-claude/pricing) · [Haiku 5.5](https://www.anthropic.com/claude-haiku-5-5)
- OpenAI: [precios](https://developers.openai.com/api/docs/pricing) · [GPT-6.2](https://openai.com/index/introducing-gpt-6-2-astra-sol/) · [GPT-6 Luna](https://developers.openai.com/api/docs/models/gpt-6-luna)
- [Agent Arena](https://arena.ai/leaderboard/agent): Google con esfuerzo High, Anthropic y OpenAI con Max; costo = mediana por tarea de los últimos 14 días; la puntuación no es el porcentaje de aciertos.

## El proceso, de principio a fin

| # | Paso | Comando | Quién |
|---|---|---|---|
| 1 | Verificar precios y marcador en las fuentes oficiales y actualizar `dados/*.csv` | — | 🧠 sesión con Nei |
| 2 | Verificar las tablas y el cálculo | `python3 calcular.py --precos` / `--arena` / `exemplos/tentativas-exemplo.csv` | ⚙️ script |
| 3 | Escribir la guía en PT (`guia/index.html`) y generar portada y banners | `gerar-capa.cjs`, `gerar-banner.sh` | 🧠 + ⚙️ Codex image_gen |
| 4 | Traducir la guía y el README al EN/ES | `traduz-pagina-codex.py html` / `readme` | ⚙️ traductor central |
| 5 | Revisión independiente de la guía | `revisor-nota.py registra --fluxo guia` | 🤖 revisor nuevo |
| 6 | Publicar: commit + push (GitHub Pages mediante Actions) | `git push` | 🧠 |
| 7 | Portal, búsqueda y catálogo PRO | habilidad `atualiza-portal` | 🧠 |
| 8 | Tema en INEMA.LLMS | habilidad `postar-telegram` | 🧠 |
| 9 | Video de la comparación en lives4 e inserción en la guía (3 idiomas) | `yt-pub-x3` | ⚙️ x3 + 🧠 |

Gratis en inema.club, directamente en internet. Licencia MIT.
