# Vragen:

## 1. Geef voor elke variabele in de dataset weer tot welk meetniveau deze behoort.

| Variabele | Meetniveau |
|---|---|
| `persoon_ID` | Nominaal |
| `geslacht` | Nominaal |
| `leeftijd` | Ratio |
| `gewicht_KG` | Ratio |
| `burgerlijke_staat` | Nominaal |
| `jaarsalaris_eu` | Ratio |
| `huishouden_grootte` | Ratio |
| `stad` | Nominaal |
| `provincie` | Nominaal |
| `opleiding_niveau` | Ordinaal |
| `autobezit` | Nominaal |
| `fietsbezit` | Nominaal |
| `elektrisch_auto` | Nominaal |
| `km_auto_per_jaar` | Ratio |
| `km_fiets_per_jaar` | Ratio |
| `km_ov_per_jaar` | Ratio |
| `km_vliegtuig_per_jaar` | Ratio |
| `dagen_thuiswerken_per_week_pro_rato` | Ratio |
| `dagen_kantoorwerken_per_week_pro_rato` | Ratio |
| `dagen_in_buitenland_per_jaar` | Ratio |
| `gebruik_carsharing` | Nominaal |
| `co2_uitstoot_per_jaar_KG` | Ratio |

---

## 2. Waarom is het nodig om vooraf te bekijken tot welk meetniveau elke variabele behoort?

Het meetniveau van een variabele bepaalt welke statistische bewerkingen en analyses je mag toepassen. Zo kun je van een nominale variabele zoals `geslacht` geen gemiddelde berekenen, maar wel een modus. Van een ratiovariabele zoals `co2_uitstoot_per_jaar_KG` kun je wel het gemiddelde, de standaardafwijking en verhoudingen berekenen. Daarnaast is het meetniveau bepalend voor welke visualisaties geschikt zijn en welke statistische toetsen je mag gebruiken. Voor machine learning is het bovendien nodig om te weten hoe variabelen getransformeerd moeten worden: nominale variabelen moeten bijvoorbeeld worden omgezet via one-hot encoding, terwijl ratio-variabelen genormaliseerd of gestandaardiseerd kunnen worden. Zonder dit vooraf te bekijken loop je het risico onjuiste conclusies te trekken of modellen te bouwen die niet correct werken.

---

## 3. Hoe ben je omgegaan met missende/niet kloppende/extreme waarden in de dataset?

Missende waarden
Detecteert welke kolommen nulls bevatten
Numeriek → imputeer met de mediaan (robuuster dan het gemiddelde bij uitschieters)
Categorisch → imputeer met de modus

Niet-kloppende waarden (negatief)
Kolommen zoals km_auto_per_jaar en jaarsalaris_eu kunnen logischerwijs nooit negatief zijn
Negatieve waarden worden vervangen door de mediaan van de geldige waarden

---

## 4. Geef een beschrijving van de 3 visualisaties met behulp van statistische termen.

### 4.1 Visualisatie 1 – Verdeling van km_auto_per_jaar 
Op de visualisatie van km_auto_per_jaar is te zien dat we te maken hebben een rechtsscheven verdeling. Er is een duidelijke aanwezigheid van uitschieters, zo kunnen we zien dat de staart sterk naar rechts loopt tot circa. 35.000 km. Dit suggereert dat de meeste personen weinig kilometers per auto reiden maar een kleine groep rijdt meer.	

### 4.2 Visualisatie 2 – Verdeling van km_fiets_per_jaar
Op de visualisatie van km_fiets_per_jaar is te zien we een normaal verdeling (mesokurtic), met een duidelijke piek rondom 2000 km. Aan de linkerkant van de grafiek zien we een duidelijke piek van het aantal mensen wat geen fiets bezit, en dus logischerwijs ook geen kilometers maakt.

### 4.3 Visualisatie 3 – Verdeling van co2_uitstoot_per_jaar_KG
Ook deze verdeling is rechtsscheef, met een hoge piek bij lage CO₂ waarden. Naast de hoge piek aan de linkerkant is er een tweede, bredere verhoging rond 5.000/10.000 kg. Dit kan erop wijzen dat er twee subgroepen in de dataset aanwezig zijn in dit geval denken we mensen met en zonder auto. 

---

## 5. Wat is de conclusie met betrekking tot de drie verdelingen?
Alle 3 de visualisaties worden sterk beïnvloed door extremen waarden rondom de 0. 
Een groot deel van de personen heeft weinig tot geen auto of fiets kilometers afgelegd dat jaar.

---

## 6. Om ervoor te zorgen dat de onafhankelijke variabelen gebruikt kunnen worden voor Machine Learning moeten ze getransformeerd worden. Geef per meetniveau aan wat er moet gebeuren.

| Meetniveau | Transformatie | Toelichting |
|---|---|---|
| **Nominaal** | One-hot encoding | Nominale variabelen hebben geen volgorde. Door ze om te zetten naar binaire kolommen (0/1) per categorie begrijpt het model de categorieën zonder een onjuiste volgorde aan te nemen. Bijvoorbeeld: `geslacht` wordt `geslacht_man` en `geslacht_vrouw`. |
| **Ordinaal** | Label encoding (of ordinal encoding) | Ordinale variabelen hebben een logische volgorde (bijv. `opleiding_niveau`: laag < midden < hoog). Deze volgorde wordt behouden door elke categorie een oplopend geheel getal toe te kennen. |
| **Ratio** | Standaardisatie (StandardScaler) of normalisatie (MinMaxScaler) | Ratiovariabelen zoals `km_auto_per_jaar` en `jaarsalaris_eu` kunnen sterk in schaal verschillen. Standaardisatie (gemiddelde = 0, std = 1) zorgt dat geen enkele variabele de andere domineert in het model. |

---

## 7. Wat kan je zeggen over de relaties tussen de variabelen?
Uit de correlatiematrix blijkt dat vooral het aantal autokilometers sterk samenhangt met de jaarlijkse CO₂ uitstoot. De correlatie tussen km_auto_per_jaar en co2_uitstoot_per_jaar_KG bedraagt 0,903. 
Dit is een zeer sterke positieve correlatie personen die meer kilometers met de auto rijden, hebben over het algemeen een aanzienlijk hogere CO₂ uitstoot. De overige numerieke variabelen hebben een veel zwakkere samenhang met de CO₂ uitstoot. 


---

## 8. Welke methode(n) heb je gebruikt en waarom?
Om de relaties tussen de numerieke variabelen te onderzoeken, is een correlatiematrix gebruikt. 
De uitkomsten zijn weergegeven in een heatmap. Daarnaast zijn de correlaties met co2_uitstoot_per_jaar_KG apart gesorteerd, zodat direct zichtbaar wordt welke numerieke variabelen het sterkst samenhangen met de afhankelijke variabele.
De correlatiematrix is geschikt omdat de onderzochte variabelen op rationiveau zijn gemeten. 
De nominale variabelen, zoals stad, autobezit en fietsbezit, kunnen niet rechtstreeks op dezelfde manier worden geïnterpreteerd in een standaard correlatiematrix. Voor het vergelijken van groepen wordt later daarom een afzonderlijke statistische toets gebruikt.



---

## 9. Geef een korte beschrijving over hoe je hebt berekend wat de kans is dat een willekeurig persoon 5000 KG CO2 uitstoot.
Om te berekenen of een willekeurig persoon meer dan 5000 kilogram CO₂ per jaar uitstoot, is er eerst gekeken naar het gemiddelde en de standaardafwijking van CO₂ uitstoot. 
	Gemiddelde: 4911,24 KG
	Standaardafwijking: 3414,94 KG 
De grenswaarde van 5000 KG is gestandaardiseerd met de z-score:

z=(x-μ)/σ  =  (5000 - 4911,24)/3424,94 ≈ 0,0260

Vervolgens is met behulp van de standaard normale verdeling de oppervlakte rechts van de z-score berekend: 
P(X>5000)=1-Φ(0,0260)≈0,4896

De geschatte kans dat een willekeurig persoon meer dan 5.000 KG CO₂ per jaar uitstoot bedraagt dus ongeveer 48,96%. 



---

## 10. Stel de hypothesen op.



---

## 11. Welke type fouten kunnen er gemaakt worden?

Bij het toetsen van een hypothese neem je een beslissing over de nulhypothese (H₀): je verwerpt de hypothese of je verwerpt het niet. Aangezien je deze beslissing baseert op een steekproef en niet op alle beschikbare data, kun je daarbij twee soorten fouten maken.

De eerste is de `Type I fout`, dit wordt ook wel het vals positief genoemd. Deze fout maak je wanneer je de nulhypothese verwerpt terwijl het in werkelijkheid waar is. Je concludeert dan dat er een effect of verschil is, terwijl dat in werkelijkheid niet het geval is. 

De tweede is de `Type II fout`, ook wel het vals negatief genoemd. Deze fout maak je wanneer je de nulhypothese niet verwerpt terwijl het in werkelijkheid onwaar is. Je mist dan een effect dat er in werkelijkheid wel bestaat. Je concludeert uiteindelijk dus dat er geen verschil of effect is, terwijl dat er wel degelijk is. 

Welke fout minder erg is, hangt volledig af van de situatie. Er is geen antwoord op de vraag welke fout beter is om te maken. Je moet per situatie afwegen wat de gevolgen zijn van een onterechte conclusie tegen het missen van een werkelijk effect. Hierop kun je uiteindelijk je onderzoek op afstemmen. 


---

## 12. Welke statistische toets moet je uitvoeren om te onderzoeken of er een significant verschil is?

De Mann-Whitney U-toets is een niet-parametrische toets die je gebruikt om te onderzoeken of er een significant verschil is tussen twee onafhankelijke groepen In tegenstelling tot de t-toets hoeft de data niet normaal verdeeld te zijn, waardoor deze toets geschikt is wanneer je data niet aan die voorwaarde voldoet. De toets vergelijkt de rangorden van de waarden in beide groepen in plaats van de gemiddelden. Wanneer de p-waarde van de toets lager is dan het gekozen significantieniveau, concludeer je dat er een significant verschil bestaat tussen de twee groepen.

---

## 13. Geef in je eigen woorden een toelichting op de betekenis van de p-waarde.

De p-waarde is een getal tussen 0 en 1 dat aangeeft hoe bijzonder je uitkomst is. Hoe lager de p-waarde, hoe opvallender je resultaat. Wanneer de p-waarde kleiner is dan het gekozen significantieniveau, kun je stellen dat de gevonden uitkomst significant genoeg is om de nulhypothese te verwerpen en er dus een echt verschil is. 

---

## 14. Welke conclusie kan je trekken op basis van de statistische toets?

Op basis van de Mann-Whitney U-toets kan geconcludeerd worden dat er een statistisch significant verschil is in CO₂-uitstoot tussen personen met en zonder autobezit. De p-waarde is kleiner dan het significantieniveau van 0,05, waardoor de nulhypothese wordt verworpen. Dit betekent dat autobezit samenhangt met een verschil in CO₂-uitstoot. Het is echter belangrijk om op te merken dat dit niet automatisch betekent dat autobezit de oorzaak is van een hogere of lagere CO₂-uitstoot de toets toont enkel aan dat er een significant verschil bestaat tussen de twee groepen, niet dat er sprake is van een oorzakelijk verband.

---

## 15. Op hoeveel verschillende mogelijkheden kan deze split gemaakt worden? Gebruik de wetenschappelijke notatie voor grote getallen. VB: 15000 = 1,5 × 10⁴

Bij een 80/20-split van 1500 observaties zijn er ongeveer 2,48 × 10³²⁴ mogelijke manieren waarop deze split gemaakt kan worden.


---

## 16. Welke metric zou je gebruiken om te toetsen hoe goed je model is en waarom?



---

## 17. Geef de wiskunde formule van het getrainde model en pas deze toe op jouw eigen situatie (kies 1 groepsgenoot).



---

## 18. Welke statistische toets(en) heb je gebruikt en waarom?



---

## 19. Wat is de conclusie van de statistische toets?



---

## 20. Welk model zou je nu kunnen gebruiken en waarom?



---

## 21. Geef de wiskunde formule van het getrainde model en pas deze toe op jouw eigen situatie (kies 1 groepsgenoot).



---

## 22. Schrijf een conclusie op basis van de twee hoofdvragen van het portfolio (zie kopje 'Vraagstellingen').


