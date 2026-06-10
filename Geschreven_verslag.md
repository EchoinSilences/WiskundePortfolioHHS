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



---

## 12. Welke statistische toets moet je uitvoeren om te onderzoeken of er een significant verschil is?



---

## 13. Geef in je eigen woorden een toelichting op de betekenis van de p-waarde.



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


