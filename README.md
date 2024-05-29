Bakalárska práca
----------------------------------------------------------------------------------------
- Názov práce: Aplikácia vhodných metód dátovej analytiky na predikciu mozgovej príhody
- Autor: Vanesa Sabolová
- Vedúci: Ing. Anna Biceková, PhD.
----------------------------------------------------------------------------------------
- použité klasifikačné modely: Nahodný les, Naivný Bayes, K-najbližších susedov, Rozhodovací strom, Logistická regresia
- použité modely zhlukovanie: K-Means
- použité Asociačné pravidlá na vybratie dôležitých atribútov datasetu (Asociačné_pravidlá.ipynb)
- použité grafy na lepšiu vizualizáciu (Grafy.ipynb)
----------------------------------------------------------------------------------------
Každý model má dva nootebooky(zošity):

1. prvý nootebook pre každý vybraný model napr. (RF_všetky_atribúty.ipynb):
   - načíta dataset stroke_data.csv
   - najprv odstránim atribút "id", ktorý nie je potrebný pre ďalšie spracovanie dát
   - premenujem si názvy atribútov z angličtiny do vhodného slovenského názvu
   - zobrazím si prvých 5 riadkov
   - chýbajúce hodnoty atribútu bmi nahradíme priemerom všetkých hodnôt tohto atribútu
   - prevediem kategorické atribúty na číselné
   - skontrolujeme počet prázdnych hodnôt v jednotlivých atribútoch
   - vyberieme všetky atribúty na ktorých následne použijeme normalizáciu
   - dáta si rozdelíme na trénovaciu a testovaciu časť (70:30)
   - vytvoríme a natrénujeme vybraný model
   - vypočítam si jednotlivé hodnoty metrík (f1, precision, recall, accuracy) a vykreslím maticu zámen
   - vypočítam si AUC (plocha pod ROC krivkou) a vykreslím ROC krivku
----------------------------------------------------------------------------------------
2. druhý nootebook pre každý vybraný model napr. (RF_AP_vylepšene.ipynb):
   - načíta dataset stroke_data.csv
   - najprv odstránim atribút "id", ktorý nie je potrebný pre ďalšie spracovanie dát
   - premenujem si názvy atribútov z angličtiny do vhodného slovenského názvu
   - zobrazím si prvých 5 riadkov
   - chýbajúce hodnoty atribútu bmi nahradíme priemerom všetkých hodnôt tohto atribútu
   - prevediem kategorické atribúty na číselné
   - skontrolujeme počet prázdnych hodnôt v jednotlivých atribútoch
   - použijem atribúty vybrané asociačnými pravidlami, ktoré normalizujem
   - dáta si rozdelím na trénovaciu a testovaciu časť (70:30)
   - vytvoríme a natrénujeme vybraný model
   - vypočítam si jednotlivé hodnoty metrík (f1, precision, recall, accuracy) a vykreslím maticu zámen
   - vypočítam si AUC (plocha pod ROC krivkou) a vykreslím ROC krivku
   - aplikujem metódu ADASYN na vyváženie dát
   - dáta znova rozdelím na trénovaciu a testovaciu časť (70:30)
   - vytvoríme a natrénujeme vybraný model už na vyvážených dátach
   - vypočítam si jednotlivé hodnoty metrík (f1, precision, recall, accuracy) a vykreslím maticu zámen na vyvážených dátach
   - znova vypočítam AUC (plocha pod ROC krivkou) a vykreslím ROC krivku
----------------------------------------------------------------------------------------
3. Zhlukovanie (K-Means.ipynb)
   - načíta dataset stroke_data.csv
   - najprv odstránim atribút "id", ktorý nie je potrebný pre ďalšie spracovanie dát
   - premenujem si názvy atribútov z angličtiny do vhodného slovenského názvu
   - zobrazím si prvých 5 riadkov
   - škálovanie vstupných premenných
   - zistenie optimálneho počtu zhlukov pomocou Silhouette score
   - trénovanie modelu s optimálnym počtom zhlukov
   - vizualizácia zhlukov
   - identifikácia rizikovej skupiny
----------------------------------------------------------------------------------------
link na vybraný dataset: https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset/data 
