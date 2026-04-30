# Asociačné pravidlá – Mortalita pacientov s COVID-19

Analýza faktorov spojených s úmrtím hospitalizovaných pacientov počas 1. a 4. vlny COVID-19 pomocou algoritmov **Apriori** a **FP-Growth**.

## Notebooky

| Súbor | Popis |
|---|---|
| `asociacne_pravidla_apriori.ipynb` | Apriori – 1. vlna |
| `asociacne_pravidla_apriori_4_vlna_.ipynb` | Apriori – 4. vlna |
| `asociacne_pravidla_fpgrowth_.ipynb` | FP-Growth – 1. vlna |
| `asociacne_pravidla_fpgrowth_4_vlna_.ipynb` | FP-Growth – 4. vlna |
| `grafy_AS_1_vlna.ipynb` | Vizualizácie – 1. vlna |
| `grafy_AS_4_vlna.ipynb` | Vizualizácie – 4. vlna |

## Inštalácia

```bash
pip install pandas numpy matplotlib seaborn scikit-learn mlxtend networkx matplotlib_venn openpyxl
```

## Dáta

Notebooky očakávajú v rovnakom adresári súbory:
- `1. vlna všetko 28-11-2024.xlsx`
- `4. vlna všetko 28-11-2024.xlsx`

> ⚠️ Dáta nie sú súčasťou repozitára z dôvodu ochrany osobných údajov (GDPR).
