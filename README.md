# Asociačné pravidlá v jednotlivých vlnách COVID-19 s optimalizovaným výberom atribútov

## Diplomová práca  
**Autorka:** Bc. Vanesa Sabolová  
**Študijný program:** Hospodárska informatika  
**Školiteľ:** Ing. Anna Biceková, PhD.  
**Konzultant:** doc. Ing. František Babič, PhD.  
**Rok:** 2026  

---

## Popis projektu

Tento repozitár obsahuje praktickú časť diplomovej práce zameranej na analýzu klinických, laboratórnych a demografických dát hospitalizovaných pacientov s ochorením COVID-19 pomocou **dolovania asociačných pravidiel (Association Rule Mining)**.

Práca je orientovaná na **deskriptívnu analytiku (unsupervised learning)**, ktorej cieľom nie je predikcia výsledku, ale identifikácia skrytých vzťahov, opakujúcich sa kombinácií atribútov a porovnanie dominantných charakteristík medzi jednotlivými vlnami pandémie.

Výskum sa zameriava najmä na pacientov vo veku **60 rokov a viac**, pričom porovnáva **1. a 4. vlnu pandémie COVID-19** s dôrazom na mortalitu, komorbidity, laboratórne ukazovatele a klinickú interpretáciu výsledných pravidiel.

---

## Hlavné ciele práce

- Analyzovať štruktúru medicínskych dát pacientov hospitalizovaných s COVID-19  
- Predspracovať a transformovať dáta podľa metodológie **CRISP-DM**  
- Realizovať optimalizovaný výber atribútov pre zvýšenie kvality a interpretovateľnosti pravidiel  
- Implementovať a porovnať algoritmy:
  - **Apriori**
  - **FP-Growth**
- Generovať asociačné pravidlá so zameraním na mortalitu a klinicky významné kombinácie  
- Vyhodnotiť pravidlá pomocou metrík:
  - Support  
  - Confidence  
  - Lift  
  - Conviction  
  - Leverage  
- Vizualizovať výsledky prostredníctvom grafov, sieťových grafov a Vennových diagramov  
- Porovnať rozdiely medzi 1. a 4. vlnou pandémie  

---

## Výskumné hypotézy

Na základe stanovených cieľov boli formulované aj výskumné hypotézy, ktoré smerovali k
overeniu významu výberu atribútov a k porovnaniu rozdielov medzi analyzovanými obdobiami
pandémie:
### H1:
Optimalizovaný výber atribútov zníži počet výsledných asociačných pravidiel pri zachovaní dôležitých vzťahov v dátach.
### H2:
Výber atribútov prispeje k zníženiu zjednodušeniu štruktúry analyzovaných dát a k prehľadnejšej interpretácii výsledných asociačných pravidiel.
### H3:
Medzi prvou a štvrtou vlnou pandémie budú pozorovateľné rozdiely v štruktúre často sa opakujúcich kombinácií klinických, laboratórnych a demografických charakteristík identifikovaných prostredníctvom asociačných pravidiel.

---

## Overovanie hypotéz

Hypotézy boli overované prostredníctvom:

- Porovnania výstupov medzi 1. a 4. vlnou  
- Analýzy metrík Support, Confidence, Lift, Conviction a Leverage  
- Porovnania výsledkov algoritmov Apriori a FP-Growth  
- Vizualizácie pravidiel pomocou grafov   
- Interpretácia dominantných pravidiel  

---

## Použitá metodológia

Projekt bol realizovaný podľa modelu **CRISP-DM (Cross Industry Standard Process for Data Mining):**

1. Pochopenie cieľa
2. Pochopenie dát
3. Príprava dát
4. Modelovanie
5. Vyhodnotenie
6. Nasadenie

---

## Dataset

Analyzované datasety obsahujú:

- Demografické údaje (vek, pohlavie)  
- Komorbidity (diabetes, kardiovaskulárne ochorenia, onkologické diagnózy, poškodenie obličiek...)  
- Laboratórne parametre (CRP, AST, ALT, koagulácia...)  
- Klinické charakteristiky hospitalizácie  
- Mortalitu pacientov

- **Dáta nie sú súčasťou repozitára z dôvodu ochrany osobných údajov pacientov (GDPR).**
- Pred spustením notebookov je potrebné umiestniť datasety do koreňového adresára projektu a prípadne upraviť premennú `DATA_PATH` v príslušnom notebooku. 

### Segmentácia:
-  prvá vlna COVID-19  
-  štvrtá vlna COVID-19    

---

## Štruktúra repozitára

### Analýza asociačných pravidiel:
- `asociacne_pravidla_apriori.ipynb` – Apriori (1. vlna)  
- `asociacne_pravidla_apriori_4_vlna_.ipynb` – Apriori (4. vlna)  
- `asociacne_pravidla_fpgrowth_.ipynb` – FP-Growth (1. vlna)  
- `asociacne_pravidla_fpgrowth_4_vlna_.ipynb` – FP-Growth (4. vlna)  

### Vizualizácie:
- `grafy_AS_1_vlna.ipynb` – Explorácia dát a grafy (1. vlna)  
- `grafy_AS_4_vlna.ipynb` – Explorácia dát a grafy (4. vlna)  

---

## Použité knižnice

- Python, Pandas, NumPy, Matplotlib, Seaborn, Mlxtend, NetworkX   

---

## Kľúčové výsledky

### 1. vlna:
Dominantné asociácie častejšie zahŕňali:
- Vyšší vek  
- Diabetes  
- Kardiovaskulárne ochorenia  
- Poškodenie obličiek  

### 4. vlna:
Výraznejšie sa objavovali:
- Onkologické diagnózy  
- Zvýšené zápalové markery  
- Poruchy zrážanlivosti krvi  
- Komplexnejšie kombinácie komorbidít  

---

## Prínos práce

- Lepšie pochopenie zmien v štruktúre pacientov medzi pandemickými vlnami  
- Identifikácia medicínsky relevantných kombinácií charakteristík  
- Zvýšenie interpretovateľnosti medicínskych dát  
- Využitie asociačných pravidiel v epidemiológii a zdravotníckej analytike  
- Podpora ďalšieho výskumu v oblasti dátovej analýzy COVID-19  

---

## Poznámky

- Projekt je založený na **unsupervised learning / association rule mining**  
- Nejde o predikčný model  
- Výsledky slúžia na analytickú a interpretačnú podporu  
- Klinická interpretácia nenahrádza medicínske rozhodovanie  

