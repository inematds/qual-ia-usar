## CSV (itens válidos, sem duplicatas)

```csv
id,data,valor
C-101,2026-11-19,1240
C-102,2026-11-19,930
C-103,2026-11-20,1000
```

## Duplicatas

| ID | Data | Valor | Situação |
| --- | --- | --- | --- |
| C-101 | 2026-11-19 | 1240 | Aparece duas vezes com dados idênticos. Mantive só uma ocorrência. |

## Itens sem valor

```csv
id,data,valor
C-104,2026-11-20,
```

O valor de C-104 consta como "ausente". Deixei esse item fora do total.

## Total válido

**3170 centavos** (1240 + 930 + 1000), o que equivale a R$ 31,70.