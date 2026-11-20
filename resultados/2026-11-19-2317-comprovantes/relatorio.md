# Teste: comprovantes

19/11/2026 23:26 · juiz: claude-cli:claude-sonnet-5-5 · com verificador automático

| Modelo | Certas | Taxa | US$ por entrega certa | Tempo mediano | Nota média |
|---|---:|---:|---:|---:|---:|
| GPT-6 Luna | 2/2 | 100% | 0.0001 | 7 s | 10.0 |
| Claude Haiku 5.5 | 2/2 | 100% | 0.0004 | 6 s | 10.0 |
| GPT-6.2 Sol | 2/2 | 100% | 0.0015 | 9 s | 10.0 |
| Claude Sonnet 5.5 | 2/2 | 100% | 0.0032 | 4 s | 10.0 |
| GPT-6.2 Astra | 2/2 | 100% | 0.0066 | 11 s | 10.0 |
| Claude Opus 5.5 | 2/2 | 100% | 0.0081 | 6 s | 10.0 |
| Gemini 4 Hydrogen | 2/2 | 100% | 0.0087 | 6 s | 9.5 |
| Claude Fable 5.2 | 2/2 | 100% | 0.0155 | 5 s | 10.0 |
| Gemini 4 Argon | não rodou | — | — | — | — |
| Gemini 4 Neon | não rodou | — | — | — | — |

**Mais barato por entrega certa:** GPT-6 Luna

Custo = tokens medidos × tabela oficial (dados/precos-*.csv), já descontadas as instruções fixas de cada assistente. Pela assinatura você não paga isso por tarefa: leia como "quanto custaria por uso".

**Não rodou** (a chamada falhou, não conta como erro do modelo): Gemini 4 Argon: falhou: HTTP Error 429: Too Many Requests; Gemini 4 Neon: falhou: HTTP Error 429: Too Many Requests

## Tentativas

| Modelo | # | Certa | Nota | Tempo | Motivo |
|---|---:|---|---:|---:|---|
| Claude Fable 5.2 | 1 | sim | 10 | 5 s | O CSV tem exatamente as três linhas válidas com datas ISO e valores em centavos corretos, aponta C-101 como duplicata contada uma só vez, separa C-104 como item |
| Claude Fable 5.2 | 2 | sim | 10 | 4 s | O CSV tem exatamente as três linhas válidas com datas ISO e valores em centavos corretos, aponta C-101 como duplicata contada uma só vez, separa C-104 como item |
| Claude Haiku 5.5 | 1 | sim | 10 | 6 s | O CSV tem exatamente as três linhas válidas com datas ISO e valores em centavos corretos, a duplicata C-101 é apontada e contada uma vez, C-104 é separado como  |
| Claude Haiku 5.5 | 2 | sim | 10 | 6 s | O CSV tem exatamente as três linhas válidas com datas ISO e valores em centavos corretos, C-101 é apontado como duplicata contada uma vez, C-104 é separado como |
| Claude Opus 5.5 | 1 | sim | 10 | 6 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) com data ISO e valor em centavos, a duplicata C-101 é apontada e contada uma só vez,  |
| Claude Opus 5.5 | 2 | sim | 10 | 7 s | O CSV tem exatamente as três linhas válidas com datas ISO e valores em centavos corretos, a duplicata C-101 é apontada e contada uma só vez, C-104 é separado co |
| Claude Sonnet 5.5 | 1 | sim | 10 | 4 s | A resposta entrega o CSV com as três linhas válidas corretas (C-101, C-102, C-103) em formato AAAA-MM-DD e valores em centavos, aponta C-101 como duplicata cont |
| Claude Sonnet 5.5 | 2 | sim | 10 | 4 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) com datas ISO e valores em centavos, a duplicata C-101 foi apontada e contada uma vez |
| GPT-6 Luna | 1 | sim | 10 | 7 s | O CSV tem exatamente as três linhas válidas com datas ISO e valores em centavos corretos, aponta C-101 como duplicata contada uma vez, separa C-104 como sem val |
| GPT-6 Luna | 2 | sim | 10 | 7 s | O CSV tem exatamente as três linhas válidas com datas ISO e valores em centavos corretos, a duplicata C-101 é apontada (contada uma vez), C-104 é separado como  |
| GPT-6.2 Astra | 1 | sim | 10 | 12 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) com datas ISO e valores em centavos, a duplicata de C-101 é apontada e contada uma ve |
| GPT-6.2 Astra | 2 | sim | 10 | 11 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) com datas ISO e valores em centavos, a duplicata C-101 é apontada e contada uma vez,  |
| GPT-6.2 Sol | 1 | sim | 10 | 9 s | O CSV tem exatamente as três linhas válidas com datas ISO e valores em centavos corretos, aponta a duplicata de C-101 contada uma vez, separa C-104 como item se |
| GPT-6.2 Sol | 2 | sim | 10 | 9 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) com datas ISO e valores em centavos, a duplicata C-101 é apontada e contada uma vez,  |
| Gemini 4 Argon | 1 | erro |  | 0 s | falhou: HTTP Error 429: Too Many Requests |
| Gemini 4 Argon | 2 | erro |  | 0 s | falhou: HTTP Error 429: Too Many Requests |
| Gemini 4 Hydrogen | 1 | sim | 10 | 5 s | O CSV tem exatamente as três linhas válidas no formato correto, a duplicata C-101 é apontada e contada uma só vez, C-104 é separado como item sem valor e o tota |
| Gemini 4 Hydrogen | 2 | sim | 9 | 7 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) com datas ISO e valores em centavos, a duplicata de C-101 é apontada e contada uma ve |
| Gemini 4 Neon | 1 | erro |  | 0 s | falhou: HTTP Error 429: Too Many Requests |
| Gemini 4 Neon | 2 | erro |  | 0 s | falhou: HTTP Error 429: Too Many Requests |
