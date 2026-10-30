---
title: "Uge 39 - DTO’er og exceptions"
date: 2026-09-21
project: "foredoomwatch"
---
## Hvad lavede jeg denne uge?

Jeg begyndte at hente data fra NVD's API. Jeg lavede NvdResponseDTO som et nested hierarki, så den lignede NVD's JSON, og testede DTO'en og API-kaldet i Main, som lykkes.

Jeg lavede også tre custom exceptions: DatabaseException, EntityNotFoundException og MissingIDException, som hver bygger på sammen logik som ApiException og extender unchecked RuntimeException 
 
Jeg begyndte også og dokumenterer methoder og klasser i javadoc, hvad de gjorde, hvad de var ment mm.

## Hvad lærte jeg?

Jeg lærte, at det var lettere at skrive DTO'erne nested først, fordi de ligner JSON'en og er lette at læse, og derefter speratere dem i deres egene klasser. 

Exceptions er ikke bare en forhindring. Ligesom anden kode kan de modelleres til at hjælpe. I stedet for en kryptisk besked kan man lave dem mere læselige, og man kan bruge dem til at tjekke værdier mm.

## Hvad var svært?

Det var svært at vurdere, hvornår en exception var for snæver, og hvornår den var for bred. Jeg brugte forholdsvis lang tid på at gennemtænke navne, som var brede nok til generel brug, men stadig snævre nok til at være fortællende.

## Hvad gør jeg anderledes næste gang?

Jeg ville nok starte med at lave custom exceptions og derefter den øvrige kode. Exceptions er over det hele, og jeg lavede dem for sent, så der er mange steder i koden, der stadig mangler at blive rettet til en mere fortællende exception frem for bare ApiException. Hvis jeg skulle starte forfra, ville det nok være noget af det første, jeg lavede.