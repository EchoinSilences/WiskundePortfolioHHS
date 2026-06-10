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
2. Niet-kloppende waarden (negatief)

Kolommen zoals km_auto_per_jaar en jaarsalaris_eu kunnen logischerwijs nooit negatief zijn
Negatieve waarden worden vervangen door de mediaan van de geldige waarden

---

## 4. Geef een beschrijving van de 3 visualisaties met behulp van statistische termen.



---

## 5. Wat is de conclusie met betrekking tot de drie verdelingen?



---

## 6. Om ervoor te zorgen dat de onafhankelijke variabelen gebruikt kunnen worden voor Machine Learning moeten ze getransformeerd worden. Geef per meetniveau aan wat er moet gebeuren.

| Meetniveau | Transformatie | Toelichting |
|---|---|---|
| **Nominaal** | One-hot encoding | Nominale variabelen hebben geen volgorde. Door ze om te zetten naar binaire kolommen (0/1) per categorie begrijpt het model de categorieën zonder een onjuiste volgorde aan te nemen. Bijvoorbeeld: `geslacht` wordt `geslacht_man` en `geslacht_vrouw`. |
| **Ordinaal** | Label encoding (of ordinal encoding) | Ordinale variabelen hebben een logische volgorde (bijv. `opleiding_niveau`: laag < midden < hoog). Deze volgorde wordt behouden door elke categorie een oplopend geheel getal toe te kennen. |
| **Ratio** | Standaardisatie (StandardScaler) of normalisatie (MinMaxScaler) | Ratiovariabelen zoals `km_auto_per_jaar` en `jaarsalaris_eu` kunnen sterk in schaal verschillen. Standaardisatie (gemiddelde = 0, std = 1) zorgt dat geen enkele variabele de andere domineert in het model. |

---

## 7. Wat kan je zeggen over de relaties tussen de variabelen?



---

## 8. Welke methode(n) heb je gebruikt en waarom?



---

## 9. Geef een korte beschrijving over hoe je hebt berekend wat de kans is dat een willekeurig persoon 5000 KG CO2 uitstoot.



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



---

## 13. Geef in je eigen woorden een toelichting op de betekenis van de p-waarde.

De p-waarde is een getal tussen 0 en 1 dat aangeeft hoe bijzonder je uitkomst is. Hoe lager de p-waarde, hoe opvallender je resultaat. Wanneer de p-waarde kleiner is dan het gekozen significantieniveau, kun je stellen dat de gevonden uitkomst significant genoeg is om de nulhypothese te verwerpen en er dus een echt verschil is. 

---

## 14. Welke conclusie kan je trekken op basis van de statistische toets?



---

## 15. Op hoeveel verschillende mogelijkheden kan deze split gemaakt worden? Gebruik de wetenschappelijke notatie voor grote getallen. VB: 15000 = 1,5 × 10⁴



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


