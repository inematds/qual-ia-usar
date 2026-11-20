## CSV (registros válidos e únicos)

```csv
id,data,valor
C-101,2026-11-19,1240
C-102,2026-11-19,930
C-103,2026-11-20,1000
```

## Duplicatas

- **C-101** (2026-11-19, 1240 centavos) aparece duas vezes. Mantive a primeira ocorrência e descartei a segunda do total.

## Itens sem valor (separados)

```csv
id,data,valor
C-104,2026-11-20,
```

## Total válido

**3170 centavos** (R$ 31,70)

Cálculo: 1240 + 930 + 1000 = 3170