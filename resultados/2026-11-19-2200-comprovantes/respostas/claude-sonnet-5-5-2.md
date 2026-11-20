## CSV válido (sem duplicatas e sem itens sem valor)

```csv
id,data,valor_centavos
C-101,2026-11-19,1240
C-102,2026-11-19,930
C-103,2026-11-20,1000
```

## Duplicatas

- **C-101** aparece 2 vezes (linhas 1 e 3), com data e valor idênticos (2026-11-19, 1240). Mantive a primeira ocorrência e descartei a repetição.

## Itens sem valor (separados)

```csv
id,data,valor_centavos
C-104,2026-11-20,
```

- **C-104**: valor "ausente". Ficou fora do total.

## Total válido

1240 + 930 + 1000 = **3170 centavos** (R$ 31,70)