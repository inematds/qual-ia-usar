# Teste: comprovantes

19/11/2026 22:02 · juiz: claude-cli:claude-sonnet-5-5 · com verificador automático

| Modelo | Certas | Taxa | US$ por entrega certa | Tempo mediano | Nota média |
|---|---:|---:|---:|---:|---:|
| GPT-6 Luna | 2/2 | 100% | 0.0001 | 9 s | 9.5 |
| Claude Haiku 5.5 | 2/2 | 100% | 0.0004 | 6 s | 10.0 |
| GPT-6.2 Sol | 2/2 | 100% | 0.0020 | 10 s | 10.0 |
| Claude Sonnet 5.5 | 2/2 | 100% | 0.0031 | 4 s | 10.0 |
| GPT-6.2 Astra | 2/2 | 100% | 0.0064 | 10 s | 9.5 |
| Claude Opus 5.5 | 2/2 | 100% | 0.0086 | 7 s | 10.0 |
| Claude Fable 5.2 | 2/2 | 100% | 0.0157 | 5 s | 10.0 |

**Mais barato por entrega certa:** GPT-6 Luna

Custo = tokens medidos × tabela oficial (dados/precos-*.csv), já descontadas as instruções fixas de cada assistente. Pela assinatura você não paga isso por tarefa: leia como "quanto custaria por uso".

## Tentativas

| Modelo | # | Certa | Nota | Tempo | Motivo |
|---|---:|---|---:|---:|---|
| Claude Fable 5.2 | 1 | sim | 10 | 4 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) com datas ISO e valores em centavos, a duplicata C-101 é apontada e contada uma vez,  |
| Claude Fable 5.2 | 2 | sim | 10 | 5 s | A resposta traz o CSV com as três linhas válidas corretas (C-101, C-102, C-103) no formato exigido, aponta C-101 como duplicata contada uma vez, separa C-104 co |
| Claude Haiku 5.5 | 1 | sim | 10 | 6 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) com datas ISO e valores em centavos, a duplicata de C-101 é apontada e contada uma só |
| Claude Haiku 5.5 | 2 | sim | 10 | 7 s | O CSV tem exatamente as três linhas válidas com datas ISO e valores em centavos corretos, a duplicata de C-101 é apontada e contada uma só vez, C-104 é separado |
| Claude Opus 5.5 | 1 | sim | 10 | 8 s | A resposta traz o CSV com exatamente C-101, C-102 e C-103 nos formatos e valores corretos, aponta C-101 como duplicata contada uma só vez, separa C-104 como ite |
| Claude Opus 5.5 | 2 | sim | 10 | 5 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) no formato pedido, a duplicata de C-101 é apontada e contada uma só vez, C-104 é sepa |
| Claude Sonnet 5.5 | 1 | sim | 10 | 4 s | O CSV tem exatamente as três linhas válidas com datas ISO e valores em centavos corretos, aponta C-101 como duplicata contada uma só vez, separa C-104 como item |
| Claude Sonnet 5.5 | 2 | sim | 10 | 4 s | O CSV tem exatamente as três linhas válidas com datas ISO e valores em centavos corretos, a duplicata C-101 foi apontada e contada uma vez, C-104 foi separado c |
| GPT-6 Luna | 1 | sim | 10 | 9 s | O CSV tem as colunas corretas com exatamente as três linhas válidas (C-101, C-102, C-103) nos formatos exigidos, a duplicata de C-101 é apontada, C-104 é separa |
| GPT-6 Luna | 2 | sim | 9 | 8 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) com datas ISO e valores em centavos, a duplicata de C-101 é apontada (segunda ocorrên |
| GPT-6.2 Astra | 1 | sim | 10 | 10 s | A resposta traz o CSV com exatamente C-101, C-102 e C-103 nos formatos e valores corretos, aponta a duplicata de C-101 contada uma vez, separa C-104 como item s |
| GPT-6.2 Astra | 2 | sim | 9 | 10 s | O CSV tem as colunas corretas e exatamente as três linhas válidas (C-101, C-102, C-103) com datas ISO e valores em centavos; a resposta aponta a duplicata de C- |
| GPT-6.2 Sol | 1 | sim | 10 | 11 s | O CSV tem exatamente as três linhas válidas corretas (C-101, C-102, C-103) com datas ISO e valores em centavos, a duplicata de C-101 é apontada e contada uma ve |
| GPT-6.2 Sol | 2 | sim | 10 | 9 s | O CSV tem exatamente as três linhas válidas corretas no formato pedido, a duplicata C-101 foi apontada e contada uma vez, C-104 foi separado como sem valor e o  |
