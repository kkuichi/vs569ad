# Asociačné pravidlá – Analýza mortality pacientov s COVID-19

Tento repozitár obsahuje Jupyter notebooky na analýzu faktorov spojených s úmrtím pacientov hospitalizovaných počas **1. a 4. vlny COVID-19**. Analýza využíva algoritmy dolovania asociačných pravidiel **Apriori** a **FP-Growth**.

---

## Obsah repozitára

| Súbor | Popis |
|---|---|
| `asociacne_pravidla_apriori.ipynb` | Asociačné pravidlá algoritmom Apriori – 1. vlna |
| `asociacne_pravidla_apriori_4_vlna_.ipynb` | Asociačné pravidlá algoritmom Apriori – 4. vlna |
| `asociacne_pravidla_fpgrowth_.ipynb` | Asociačné pravidlá algoritmom FP-Growth – 1. vlna |
| `asociacne_pravidla_fpgrowth_4_vlna_.ipynb` | Asociačné pravidlá algoritmom FP-Growth – 4. vlna |
| `grafy_AS_1_vlna.ipynb` | Exploratívna analýza a vizualizácie – 1. vlna |
| `grafy_AS_4_vlna.ipynb` | Exploratívna analýza a vizualizácie – 4. vlna |

---

## Cieľ analýzy

Cieľom je identifikovať kombinácie klinických, demografických a laboratórnych faktorov, ktoré sú štatisticky asociované s úmrtím pacienta (`Zomrel = 1`). Výsledné pravidlá majú tvar:

```
faktor(y) → Zomrel
```

---

## Metodológia

Každý analytický notebook (Apriori / FP-Growth) vykonáva tieto kroky:

1. **Načítanie datasetu** – z Excel súboru (1. alebo 4. vlna)
2. **Vytvorenie cieľového atribútu** – `Zomrel` odvodený zo stĺpca `Závažnosť priebehu ochorenia` (hodnota 3 = úmrtie)
3. **Čistenie dát** – odstránenie identifikačných a nerelevantných stĺpcov (meno, kódy príjmu/prepustenia, voľný text z epikrízy a pod.)
4. **Imputácia chýbajúcich hodnôt** – robustná MICE metóda (`IterativeImputer` zo scikit-learn)
5. **Tvorba vekových kategórií** – vrátane kategórie seniorov 80+
6. **Výber atribútov** – automatický výber štatisticky významných premenných (chi-kvadrát test, Spearmanov korelačný koeficient)
7. **Laboratórne markery** – použité výhradne posledné známe merania (napr. `S-Urea_Vysoke`)
8. **Generovanie asociačných pravidiel** – algoritmom Apriori alebo FP-Growth cez knižnicu `mlxtend`

Notebooky `grafy_AS_*` obsahujú exploratívnu analýzu: rozdelenie pacientov podľa pohlavia, veku, mortality a ďalších charakteristík s vizualizáciami (histogramy, countploty, sieťové grafy).

---

## Požiadavky

### Python verzia
Python 3.8+

### Potrebné knižnice

```bash
pip install pandas numpy matplotlib seaborn scikit-learn mlxtend networkx matplotlib_venn openpyxl
```

Alebo jednorázovo v notebooku:

```python
%pip install mlxtend networkx openpyxl matplotlib_venn
```

---

## Dáta

Notebooky očakávajú nasledujúce Excel súbory v rovnakom adresári:

- `1. vlna všetko 28-11-2024.xlsx` – dataset pacientov z 1. vlny
- `4. vlna všetko 28-11-2024.xlsx` – dataset pacientov zo 4. vlny

> ⚠️ **Dáta nie sú súčasťou repozitára** z dôvodu ochrany osobných údajov pacientov (GDPR). Pred spustením notebookov je potrebné umiestniť datasety do koreňového adresára projektu a prípadne upraviť premennú `DATA_PATH` v príslušnom notebooku.

---

## Spustenie

```bash
# Klonuj repozitár
git clone https://github.com/<tvoj-username>/<nazov-repozitara>.git
cd <nazov-repozitara>

# Nainštaluj závislosti
pip install -r requirements.txt

# Spusti Jupyter
jupyter notebook
```

---

## Štruktúra výstupov

Každý analytický notebook generuje:
- tabuľku asociačných pravidiel (podpora, spoľahlivosť, lift)
- vizualizácie pravidiel ako sieťový graf (`networkx`)
- Vennov diagram pre porovnanie pravidiel

---

## Autori

Projekt vznikol ako súčasť výskumnej analýzy COVID-19 hospitalizácií.

---

## Licencia

Kód je dostupný pod licenciou [MIT](LICENSE). Dáta pacientov nie sú verejne dostupné.
