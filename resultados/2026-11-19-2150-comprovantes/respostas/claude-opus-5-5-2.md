**CSV (itens válidos, sem duplicatas)**

```csv
id,data,valor
C-101,2026-11-19,1240
C-102,2026-11-19,930
C-103,2026-11-20,1000
```

**Duplicatas**

| ID | Data | Valor | Observação |
| --- | --- | --- | --- |
| C-101 | 2026-11-19 | 1240 | A 3ª linha repete a 1ª (mesmo ID, data e valor). Mantive apenas uma ocorrência. |

**Itens sem valor**

```csv
id,data,valor
C-104,2026-11-20,
```

C-104 tem o valor "ausente". Ficou fora do total e deixei o campo vazio, sem usar 0.

**Total válido: 3170 centavos** (1240 + 930 + 1000), ou seja, R$ 31,70.