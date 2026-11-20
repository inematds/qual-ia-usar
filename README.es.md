# ⚖️ Qué IA usar - GEMINI - GPT - CLAUDE

**🇧🇷 [Português](README.md) · 🇺🇸 [English](README.en.md) · 🇪🇸 [Español](README.es.md)**

[![Qué IA resulta más barata](guia/assets/banner-es.jpg)](https://inematds.github.io/qual-ia-usar/guia/es/)

## Qué es

Este proyecto compara diez modelos de IA de tres empresas: Gemini 4 de Google (Neon, Argon e Hydrogen), Claude de Anthropic (Fable, Opus, Sonnet y Haiku) y los modelos de OpenAI que usa Codex (Astra, Sol y Luna). Reúne las tablas oficiales de precios y el marcador de Agent Arena, un ranking público que mide agentes de IA realizando tareas reales, consultados el 19/11/2026. Está pensado para quienes pagan por IA y quieren elegir sin desperdiciar dinero. Para leerlo, no necesitas nada. Para probarlo con una tarea propia, basta con las apps que ya usas (ChatGPT, Claude o Gemini) o con el kit de pruebas, que ejecuta la misma tarea en todas las IA que conectes y te dice cuál acertó más y gastó menos.

## 📖 Guía

Guía completa, en lenguaje sencillo: **https://inematds.github.io/qual-ia-usar/guia/es/**

## La idea en una línea

La IA más barata de la tabla puede salirte más cara en la factura. Lo que importa es el **costo por entrega correcta**: todo lo que pagaste, incluidos los intentos fallidos, dividido entre las tareas que quedaron correctas.

## Quién gana en cada rango (19/11/2026)

Precio en US$ por millón de tokens (entrada / salida). Puntuación y costo por tarea: Agent Arena.

| Rango | Google | Anthropic | OpenAI |
|---|---|---|---|
| Trabajo complejo | Gemini 4 Neon · 3 / 15 · Puntuación 1333 · US$ 2,60 por tarea | Claude Opus 5.5 · 4 / 20 · 1336 · US$ 5,98 | GPT-6.2 Astra · 8 / 40 · 1291 · US$ 3,11 |
| Día a día | Gemini 4 Argon · 2 / 10 (4 / 20 a partir del 1 de diciembre) · 1229 · US$ 0,66 | Claude Sonnet 5.5 · 2 / 10 · 1296 · US$ 3,27 | GPT-6.2 Sol · 2 / 10 · 1241 · US$ 0,96 |
| Gran volumen | Gemini 4 Hydrogen · 1,50 / 7,50 · 1271 (preliminar) · US$ 1,50 | Claude Haiku 5.5 · 0,10 / 0,50 · sin puntuación | GPT-6 Luna · 0,10 / 0,50 · sin puntuación |

Fuera de los rangos: **Claude Fable 5.2** (US$ 8 / 40) lidera el marcador con una puntuación de 1448 y cuesta US$ 9,16 por tarea.

- **Complejo:** Neon casi empata con Opus y cuesta menos de la mitad por tarea.
- **Día a día:** los tres cobran lo mismo por token; por tarea, Argon sale más barato y Sonnet tiene la mejor puntuación.
- **Volumen:** Haiku y Luna cobran 15 veces menos por token que Hydrogen; su calidad solo se descubre al probarlos.
- **Dentro de Google:** Hydrogen es más barato por token que Argon, pero costó más del doble por tarea.

Lo que promete esta comparación: las cifras de los rangos son las publicadas (la prueba propia, más abajo, cubre una tarea y siete modelos), el marcador mide tareas de agentes en general, no las tuyas, y todo cambia con el tiempo.

## Cómo empezar (sin programar)

Abre Claude Code o Codex en una carpeta tuya y pega esto:

```text
Lee el proyecto "Qual IA usar" en https://github.com/inematds/qual-ia-usar (el README explica el kit de pruebas en kit/testar.py).
Quiero saber qué IA resulta más barata por entrega correcta en una tarea mía: [describe la tarea y qué significa que "quedó bien"].
1. Dime, en español sencillo, qué 3 o 4 modelos vale la pena probar para esa tarea y por qué.
2. Propón una prueba pequeña: cuántas veces ejecutar cada modelo y cuánto debería costar.
3. No llames a ningún modelo ni gastes nada antes de que yo diga que sí.
Después de que diga que sí, prepara la tarea en el formato del kit (kit/testar.py), ejecuta la prueba y muéstrame el informe.
```

## Kit de pruebas: tu tarea en todas las IA

Describes la tarea y qué significa que "quedó bien". El kit ejecuta la misma tarea en cada IA varias veces, evalúa cada respuesta (con un juez de IA y, si quieres, un verificador automático) y devuelve un informe: cuántas quedaron correctas, tiempo y costo por entrega correcta.

**Prueba real (19/11/2026, tarea de los comprobantes, 2 veces cada una, todas con suscripción: Claude con Claude Code, GPT con Codex, Gemini con Google AI Pro mediante Antigravity CLI):**

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

En una tarea sencilla, todos aciertan, así que gana el más barato. Los tres Gemini se ejecutaron con esfuerzo **high** (el mismo del marcador) y piensan bastante antes de responder (de 1.600 a 2.900 tokens de salida); Claude y GPT se ejecutaron con el esfuerzo predeterminado de cada asistente. Con API y esfuerzo predeterminado, Hydrogen costó US$ 0,0087 por entrega (unas 2,5 veces menos). Al principio se rechazó una respuesta de Fable por un error del verificador; se corrigió y se volvió a evaluar con `--reavaliar`. Informe completo: [resultados/2026-11-19-2317-comprovantes (en portugués)](resultados/2026-11-19-2317-comprovantes/relatorio.md).

## En la práctica: cómo elige Nei

- **Luna y Haiku:** cuestan centavos y acertaron la tarea sencilla. Una buena opción para una ejecución sencilla y larga (muchos pasos repetidos, gran volumen).
- **Terra y Sonnet:** en las pruebas de Nei, sus preferidos son GPT-6.1 Terra y Claude Sonnet 5.5. Cuestan más, pero ofrecen buenos resultados con mayor constancia. En OpenAI, de menor a mayor: Luna, Terra, Sol y Astra. Terra no está en las tablas de este proyecto.
- **Neon como crítico:** hoy Nei usa Claude y Codex para revisarse mutuamente, porque los modelos de empresas diferentes se equivocan en puntos diferentes. Gemini 4 Neon puede ser la IA que valida y critica para quienes solo tienen Claude o solo Codex (cómo conectarlo: sección siguiente).

## Gemini Pro dentro de Claude Code o Codex

**Gemini CLI fue retirado.** El 18/06/2026 Google dejó de aceptar en Gemini CLI las cuentas con suscripción a Google AI Pro o Ultra (y el uso individual gratuito). Al iniciar sesión aparece: *"This client is no longer supported for Gemini Code Assist for individuals… migrate to the Antigravity suite"*. El sustituto es **Antigravity CLI (`agy`)**, que usa la cuota de tu suscripción. La clave de API de AI Studio no usa la suscripción: tiene su propia cuota, y en el plan gratuito Neon y Argon responden con 429.

**El proceso que seguimos (19/11/2026):**

1. Claves de API de Gemini que ya existían (plan gratuito): Hydrogen respondió; Neon y Argon devolvieron `429 You exceeded your current quota`.
2. Gemini CLI 0.70.0 con inicio de sesión en la cuenta de la suscripción: inicio aceptado, uso rechazado (mensaje anterior).
3. Antigravity CLI 1.5.13: instalado; se inició sesión con la cuenta de Google (enlace → código pegado de vuelta); `agy models` mostró Gemini 4 Neon, Argon e Hydrogen (de low a xhigh), Gemini 3.8 Flash, Claude Opus 5.5 y Sonnet 5.5.
4. El kit de pruebas incorporó la vía `agy` y ejecutó los tres Gemini con la suscripción.

**Cómo hacerlo:**

```bash
# 1. instalar (el script descarga el binario y verifica el SHA-512)
curl -fsSL https://antigravity.google/cli/install.sh | bash      # instala en ~/.local/bin/agy

# 2. iniciar sesión: ejecuta sin argumentos, elige "Google OAuth", abre el enlace e inicia sesión con la cuenta que tiene la suscripción a Gemini
agy                                                                # luego pega el código de autorización

# 3. ver qué habilita tu cuenta
agy models

# 4. usar sin interacción (así lo llaman Claude Code, Codex y el kit)
agy -p "Critica este texto: ..." --model gemini-4-neon-high --output-format json
```

La salida JSON incluye `response`, `duration_seconds` y `usage` (tokens de entrada, salida y razonamiento). Dentro de Claude Code o Codex, basta con pedirle a la IA que llame a `agy` desde la terminal. Un buen uso es Neon como segunda opinión: Claude o Codex hacen el trabajo y Gemini lo critica.

En el kit, `kit/motores.json` ya dirige los tres Gemini a la vía `agy` (`gemini-4-neon-high`, `gemini-4-argon-high`, `gemini-4-hydrogen-high`).

**Precauciones:** la cuota de Pro no tiene una cifra publicada (se renueva cada 5 horas, con un límite semanal); hay informes de cuentas Pro que reciben "not eligible" en Antigravity; con esfuerzo alto, Gemini piensa y escribe más, lo que encarece el costo equivalente por uso.

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
 "criterio": "cómo es que 'quedó bien', punto por punto",
 "verificar": "python3 verificar.py",
 "repeticoes": 3}
```

`verificar` es opcional: un comando que recibe la ruta de la respuesta y termina con 0 cuando es correcta. La respuesta solo cuenta como correcta si pasa el verificador **y** el juez.

**Los modelos** están en `kit/motores.json` (`modelo` coincide con el nombre en `dados/precos-*.csv`, `via`, `id`). Vías:

| Vía | Cómo se invoca | Se necesita |
|---|---|---|
| `claude-cli` | `claude -p`, sin herramientas | Claude Code con sesión iniciada (suscripción) |
| `codex-cli` | `codex exec`, sandbox de solo lectura | Codex con sesión iniciada (suscripción) |
| `agy` | `agy -p`, Antigravity CLI | Inicio de sesión con la cuenta de Google que tiene la suscripción a Gemini (AI Pro/Ultra) |
| `gemini-cli` | `gemini -p` | Solo con clave de API de pago: la suscripción individual migró a `agy` |
| `api-anthropic`, `api-openai`, `api-google`, `openrouter` | API HTTP | `ANTHROPIC_API_KEY`, `OPENAI_API_KEY`, `GEMINI_API_KEY`, `OPENROUTER_API_KEY` |

El costo se calcula con los tokens medidos × la tabla oficial. Claude Code, Codex y Gemini CLI agregan instrucciones propias a cada pedido; el kit mide ese agregado una vez por modelo y lo descuenta (el número bruto queda en la columna `tokens_entrada_bruto`). Con una suscripción no pagas por tarea: interpreta el costo como «cuánto costaría por uso». Las llamadas que fallan (cuota, red, inicio de sesión) aparecen como «no se ejecutó» y no cuentan como errores del modelo. Las vías `claude-cli`, `codex-cli`, `agy` y `api-google` se probaron de verdad; `api-anthropic`, `api-openai`, `openrouter` y `gemini-cli` solo contra un servidor falso. Consulta el `id` de cada modelo en la documentación de la empresa.

Los resultados se guardan en `resultados/<data>-<nombre>/`: las respuestas, `tentativas.csv` (que `calcular.py` también lee) y `relatorio.md`.

### Archivos

| Archivo | Qué es |
|---|---|
| `calcular.py` | Calcula el costo por entrega correcta a partir de un CSV de intentos |
| `dados/precos-2026-11-19.csv` | Precios oficiales por millón de tokens, con la fuente de cada fila |
| `dados/arena-2026-11-19.csv` | Puntuación y costo mediano por tarea en Agent Arena (corte del 19/11/2026) |
| `exemplos/tentativas-exemplo.csv` | Ejemplo **ficticio** de prueba (no es una medición) |
| `kit/testar.py` | Kit de pruebas: ejecuta la tarea en cada IA, evalúa y calcula el costo por entrega correcta |
| `kit/motores.json` | Lista de modelos y cómo invocar cada uno |
| `kit/exemplo-comprovantes/` | Tarea de ejemplo con verificador automático |
| `resultados/` | Informes de pruebas ya ejecutadas |
| `guia/` | La guía en PT, EN y ES (GitHub Pages) |

### Formato del CSV de intentos

Una fila por intento:

| Columna | Qué contiene |
|---|---|
| `modelo` | Igual al nombre en `dados/precos-2026-11-19.csv` (p. ej., `Gemini 4 Argon`) |
| `execucao` | Etiqueta de cada vez que diste la tarea desde cero (1, 2, 3…). Las correcciones de una misma ejecución suman costo y cuentan como una entrega |
| `tokens_entrada`, `tokens_saida` | Tokens gastados en el intento |
| `custo_usd` | Importe cobrado, si el panel lo muestra. Vacío = se calcula con los tokens y la tabla |
| `aprovada` | `sim` o `não`. La ejecución cuenta como entrega si se aprobó alguno de sus intentos |

La falta de costo nunca se convierte en cero: el modelo aparece como «sin costo» y queda fuera de la comparación.

### Cómo se calcula

`costo por entrega correcta = suma del costo de todos los intentos ÷ número de ejecuciones aprobadas`

Para probar con tareas listas y datos ficticios, usa el protocolo del laboratorio de Gemini 4: [protocolo.md (en portugués)](https://github.com/inematds/gemini-4-na-pratica/blob/main/laboratorio/protocolo.md).

## Fuentes

- Google: [precios](https://aistudio.google.com/docs/pricing) · [Neon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) · [Argon](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-argon/) · [Hydrogen](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/)
- Anthropic: [precios](https://platform.claude.com/docs/en/about-claude/pricing) · [Haiku 5.5](https://www.anthropic.com/claude-haiku-5-5)
- OpenAI: [precios](https://developers.openai.com/api/docs/pricing) · [GPT-6.2](https://openai.com/index/introducing-gpt-6-2-astra-sol/) · [GPT-6 Luna](https://developers.openai.com/api/docs/models/gpt-6-luna)
- [Agent Arena](https://arena.ai/leaderboard/agent): Google con esfuerzo High, Anthropic y OpenAI con Max; costo = mediana por tarea de los últimos 14 días; la puntuación no es un porcentaje de aciertos.

## El proceso, de principio a fin

| # | Paso | Comando | Quién |
|---|---|---|---|
| 1 | Verificar precios y marcador en las fuentes oficiales y actualizar `dados/*.csv` | — | 🧠 sesión con Nei |
| 2 | Verificar las tablas y los cálculos | `python3 calcular.py --precos` / `--arena` / `exemplos/tentativas-exemplo.csv` | ⚙️ script |
| 3 | Escribir la guía PT (`guia/index.html`) y generar portada y banners | `gerar-capa.cjs`, `gerar-banner.sh` | 🧠 + ⚙️ Codex image_gen |
| 4 | Traducir la guía y el README a EN/ES | `traduz-pagina-codex.py html` / `readme` | ⚙️ traductor central |
| 5 | Revisión independiente de la guía | `revisor-nota.py registra --fluxo guia` | 🤖 revisor nuevo |
| 6 | Publicar: commit + push (GitHub Pages mediante Actions) | `git push` | 🧠 |
| 7 | Portal, búsqueda y catálogo PRO | skill `atualiza-portal` | 🧠 |
| 8 | Tema en INEMA.LLMS | skill `postar-telegram` | 🧠 |
| 9 | Video de la comparación en lives4 e inserción en la guía (3 idiomas) | `yt-pub-x3` | ⚙️ x3 + 🧠 |

Gratis en inema.club, directamente en internet. Licencia MIT.
