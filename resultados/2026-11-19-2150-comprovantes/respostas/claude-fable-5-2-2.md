## CSV (comprovantes válidos, sem duplicatas)

```csv
id,data,valor_centavos
C-101,2026-11-19,1240
C-102,2026-11-19,930
C-103,2026-11-20,1000
```

## Duplicatas

O **C-101** aparece duas vezes (linhas 1 e 3), com a mesma data e o mesmo valor (19/11/2026, R$ 12,40). Mantive apenas a primeira ocorrência e descartei a da linha 3.

## Itens sem valor

Separei o C-104, que está com valor "ausente" e não entra no total:

```csv
id,data,valor_centavos
C-104,2026-11-20,
```

## Total válido

1240 + 930 + 1000 = **3170 centavos** (R$ 31,70)