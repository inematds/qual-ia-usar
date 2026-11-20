## CSV (itens válidos)

```csv
id,data,valor_centavos
C-101,2026-11-19,1240
C-102,2026-11-19,930
C-103,2026-11-20,1000
```

## Duplicatas

- **C-101** aparece 2 vezes (19/11/2026, R$ 12,40), com os mesmos dados. Mantive a primeira ocorrência e descartei a repetição (linha 3).

## Itens sem valor (separados)

```csv
id,data,valor_centavos
C-104,2026-11-20,
```

- **C-104** (20/11/2026): valor "ausente". Ficou fora do total.

## Total válido

1240 + 930 + 1000 = **3170 centavos** (R$ 31,70)