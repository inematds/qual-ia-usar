# Teste: comprovantes

19/11/2026 21:51 · juiz: claude-cli:claude-sonnet-5-5 · com verificador automático

| Modelo | Certas | Taxa | US$ por entrega certa | Tempo mediano | Nota média |
|---|---:|---:|---:|---:|---:|
| GPT-6 Luna | 2/2 | 100% | 0.0001 | 7 s | 9.0 |
| Claude Haiku 5.5 | 2/2 | 100% | 0.0004 | 6 s | 10.0 |
| GPT-6.2 Sol | 2/2 | 100% | 0.0014 | 9 s | 9.5 |
| Claude Sonnet 5.5 | 2/2 | 100% | 0.0031 | 4 s | 10.0 |
| GPT-6.2 Astra | 2/2 | 100% | 0.0064 | 10 s | 9.5 |
| Claude Opus 5.5 | 2/2 | 100% | 0.0086 | 7 s | 10.0 |
| Claude Fable 5.2 | 2/2 | 100% | 0.0181 | 5 s | 10.0 |

**Mais barato por entrega certa:** GPT-6 Luna

Custo = tokens medidos × tabela oficial (dados/precos-*.csv), já descontadas as instruções fixas de cada assistente. Pela assinatura você não paga isso por tarefa: leia como "quanto custaria por uso".

## Tentativas

| Modelo | # | Certa | Nota | Tempo | Motivo |
|---|---:|---|---:|---:|---|
| Claude Fable 5.2 | 1 | sim | 10 | 5 s | O CSV tem exatamente as três linhas válidas com datas ISO e valores em centavos corretos, aponta a duplicata de C-101 (contada uma vez), separa C-104 como item  |
| Claude Fable 5.2 | 2 | sim | 10 | 6 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) com datas ISO e valores em centavos, a duplicata de C-101 é apontada e contada uma ve |
| Claude Haiku 5.5 | 1 | sim | 10 | 6 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) com datas ISO e valores em centavos, a duplicata C-101 é apontada e contada uma vez,  |
| Claude Haiku 5.5 | 2 | sim | 10 | 6 s | O CSV tem exatamente as três linhas válidas com datas ISO e valores em centavos corretos, a duplicata C-101 é apontada e contada uma vez, C-104 é separado como  |
| Claude Opus 5.5 | 1 | sim | 10 | 6 s | O CSV tem exatamente as três linhas válidas com datas ISO e valores em centavos corretos, a duplicata de C-101 é apontada e contada uma vez, C-104 está separado |
| Claude Opus 5.5 | 2 | sim | 10 | 8 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) com datas ISO e valores em centavos, a duplicata de C-101 é apontada e contada uma ve |
| Claude Sonnet 5.5 | 1 | sim | 10 | 3 s | O CSV traz exatamente as três linhas válidas com datas ISO e valores em centavos corretos, a duplicata C-101 é apontada e contada uma só vez, C-104 é separado c |
| Claude Sonnet 5.5 | 2 | sim | 10 | 6 s | O CSV tem exatamente as três linhas válidas com datas ISO e valores em centavos corretos, a duplicata C-101 é apontada e contada uma vez, C-104 é separado como  |
| GPT-6 Luna | 1 | sim | 9 | 7 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) com datas ISO e valores em centavos, aponta a duplicata de C-101, separa C-104 como s |
| GPT-6 Luna | 2 | sim | 9 | 7 s | O CSV tem as três linhas válidas corretas (C-101, C-102, C-103) em formato ISO e centavos, aponta a duplicata de C-101, separa C-104 como sem valor e informa o  |
| GPT-6.2 Astra | 1 | sim | 9 | 11 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) com datas ISO e valores em centavos, a duplicata de C-101 é apontada e contada uma ve |
| GPT-6.2 Astra | 2 | sim | 10 | 9 s | O CSV tem as colunas corretas e exatamente as três linhas válidas (C-101, C-102, C-103) com datas ISO e valores em centavos; a resposta aponta a duplicata de C- |
| GPT-6.2 Sol | 1 | sim | 9 | 9 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) com datas ISO e valores em centavos, aponta a duplicata de C-101 excluída, separa C-1 |
| GPT-6.2 Sol | 2 | sim | 10 | 8 s | O CSV tem exatamente as três linhas válidas com datas ISO e valores em centavos corretos, aponta C-101 como duplicata contada uma vez, separa C-104 como item se |
