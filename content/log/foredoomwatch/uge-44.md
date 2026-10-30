---
title: "Uge 44 - README og exceptions"
date: 2026-10-26
project: "foredoomwatch"
---
## Hvad lavede jeg denne uge?

Jeg arbejdede mest på dokumentationen. Jeg reviderede README'en mandag og udvidede den torsdag med projektdetaljer og arkitektur, og jeg rettede linket til repoet. Jeg lavede også en flowtest.http, som viser, hvordan API'et bruges.

Jeg ændrede, hvordan en DAO exception ser ud. DatabaseException fik en ny konstruktør med en årsag og uden HTTP-status, og HostController oversætter den nu til en ApiException med status 500. Det gjorde jeg som et eksempel i HostDAO, for hvordan det faktiks burde se ud. 

## Hvad var svært?

Det var svært at rette exceptions så sent i projektet, og jeg prioteret at dokumentere og skrive readme i stedet. Jeg nåede kun at ændre et sted, HostDAO, som et eksempel på, hvordan det burde se ud. 

## Hvad gør jeg anderledes næste gang?

Jeg ville selvfølgelig være mere opmærksom på, hvor jeg bruger HTTP-statuskoder. Jeg vidste godt, at de burde ligge i controlleren, men jeg var for uopmærksom, og det påvirkede projektet kvalitet.