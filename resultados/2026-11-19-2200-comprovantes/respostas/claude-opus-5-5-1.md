## CSV (itens válidos, sem duplicatas)

```csv
id,data,valor_centavos
C-101,2026-11-19,1240
C-102,2026-11-19,930
C-103,2026-11-20,1000
```

## Duplicatas

| ID | Data | Valor (centavos) | Ocorrências | Tratamento |
| --- | --- | --- | --- | --- |
| C-101 | 2026-11-19 | 1240 | 2 (linhas 1 e 3) | Os registros são idênticos. Mantive um e descartei a cópia. |

## Itens sem valor (separados)

```csv
id,data,valor_centavos
C-104,2026-11-20,
```

O valor de C-104 está "ausente". Deixei o campo vazio em vez de 0 para não confundir com um comprovante de valor zero. Ele ficou fora do total.

## Total válido

1240 + 930 + 1000 = **3170 centavos** (R$ 31,70)