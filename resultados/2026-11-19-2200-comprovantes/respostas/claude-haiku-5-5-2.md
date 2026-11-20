## CSV (registros válidos, sem duplicata)

```csv
id,data,valor_centavos
C-101,2026-11-19,1240
C-102,2026-11-19,930
C-103,2026-11-20,1000
```

## Duplicatas

- **C-101** aparece duas vezes, com a mesma data (2026-11-19) e o mesmo valor (1240 centavos). Mantive apenas a primeira ocorrência no CSV.

## Sem valor

```csv
id,data,valor_centavos
C-104,2026-11-20,
```

## Total válido

**3170 centavos** (R$ 31,70), somando C-101, C-102 e C-103. Se a duplicata de C-101 fosse contada, o total seria 4410 centavos, mas isso representaria uma cobrança repetida.