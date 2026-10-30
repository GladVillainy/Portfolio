---
title: "Uge 37 - Mockup, skærmkort og generisk DAO"
date: 2026-09-07
project: "foredoomwatch"
---
## Hvad lavede jeg denne uge?

Sammen med en AI-agent etablerede jeg en generisk asset- og vulnerability-hjemmeside. Det var det første skridt mod at få noget visuelt op at stå, og jeg tænkte det var vigtigt at starte generisk, hvorefter jeg kunne udfylde og justere den efter systemets behov, såsom at tildele features.

Jeg arbejdede også på en generisk DAO. Med en lang række entities vil der komme mange DAO-klasser med meget repetitiv kode, og for at undgå dette kom jeg med en løsning, som var at lave en generisk DAO. DAO'en tager typen T samt typen på ID'et og indeholder CRUD-metoderne Create(), Read(), Update() og Delete(), samt en tilføjet ReadAll().

Jeg testede DAO'en med JUnit 5-integrationstests på UserDAO og HostDAO, hvor databasen ryddes før hver test for et rent udgangspunkt. Testene fandt en del bugs, som jeg rettede metode for metode: først create, så delete og readAll. Derefter tilføjede jeg exception-håndtering på alle metoderne og opdaterede testene, så de også dækker exception-vejen.

Håndteringen sker via try/catch og throw. Jeg fanger en PersistenceException, som er unchecked (RuntimeException), og udfolder den til en ApiException med HTTP-status 500, Internal Server Error, fordi det er et tilfælde, hvor noget går galt fra serverens side. Der bruges også rollback for at forhindre skader i databasen.

Til sidst begyndte jeg på API-kommunikationen med klassen APIUtils og metoden ReadAPI.

## Hvad lærte jeg?

Jeg synes jeg fik et godt resultat, og er tilfreds med det indtil videre. Jeg lærte meget om exceptions, håndtering af dem, samt HTTP-protokoller.

## Hvad var svært?

Det var lige at holde tungen lige i munden at håndtere de mange exceptions og overskue, hvor ting kunne gå galt. Det er vigtigt at skrive robust kode, da runtime exceptions crasher koden, men også fordi exception-håndtering er vigtigt i praksis. Det fortæller det mere specifikke problem, frem for det ofte kryptiske man ellers får ud, når en uhåndteret exception rammer.

## Hvad gør jeg anderledes næste uge?

Exception-håndtering er klart noget jeg gerne vil blive bedre til, da det er essentielt.

