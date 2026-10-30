---
title: "Uge 42 - Ejerskab, tråde og tests, og efterårsferie"
date: 2026-10-12
project: "foredoomwatch"
---
## Hvad lavede jeg denne uge?

Jeg begyndte ugen med at fjerne støj fra scanningerne. Jeg lavede metoder i vulnerability og finding-DAO'en, der tjekker, om noget allerede findes, og filtrerer i servicen, så der ikke oprettes dubletter.

Derefter lavede jeg en ownership exception, som tjekker, at brugeren ejer den host eller software, der bliver tilgået, og brugte den på metoderne i controllerne. Jeg lavede en samlet CVSS-sorteringsmetode, der deler sig i accende og dessending rækkefølge.

Onsdag lavede jeg en scheduler, der med tråde poller NVD's API, og torsdag håndterede jeg NVD's 403-svar og tilføjede en forsinkelse mellem scanninger. Fredag skrev jeg REST Assured-tests af routes på software, finding og vulnerability.

## Hvad lærte jeg?

Jeg lærte, at tests finder fejl, som man ikke selv opdager. Da jeg testede mandag, fik jeg et 500-svar, fordi finding manglede et ejerskabstjek. Jeg lærte også, hvordan man kan køre en opgave i en separat tråd på et fast interval, så scanninger sker af sig selv.

## Hvad var svært?

Det var svært at få polling til at passe sammen med NVD's begrænsninger. Når for mange kald blev sendt for hurtigt, svarede NVD med 403, så jeg måtte tilføje en forsinkelse mellem scanninger og håndtere fejlen.

## Hvad gør jeg anderledes næste gang?

Jeg ville skrive testene tidligere. Ejerskabsfejlen blev først opdaget, da jeg testede, men den kunne være fundet tidligere, og burde også have været plangt fra start af. 