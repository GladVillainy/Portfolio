---
title: "Uge 40 - CPE-match og mappers"
date: 2026-09-28
project: "foredoomwatch"
---
## Hvad lavede jeg denne uge?

Jeg arbejdede videre på NVD-integrationen og prioriterede at matche software med Common Platform Enumeration (CPE). Et CPE-match kræver tre parametre: vendor, product og version. Keyword search gav ikke mening, fordi den kun kan finde produktet og ikke et specifikt versionsnummer, så man får alle CVE'er for produktet på tværs af versioner. Derfor ændrede jeg søgningen til en virtualMatchString med versionen og lavede en Service-klasse, der finder sårbarheder, opretter findings og gemmer dem i databasen.

Jeg lavede entiteterne Metrics og Reference, en VulnerabilityDAO og en VulnerabilityMapper, og jeg delte DTO'erne op, så hver gren af JSON'en fik sin egen DTO. Derefter lavede jeg DTO'er og mappers til de øvrige entiteter bag et fælles interface, IMapper, og lagde NVD-mapperen i sin egen klasse.

Jeg fortsatte også med at ændre mine custom unchecked exceptions, så de indeholder en HTTP-enum og en besked. Til sidst tilføjede jeg hashing af passwords med BCrypt og testede det i GenericDAOTest.

## Hvad lærte jeg?

Jeg sammenlignede readAPI med Jackson og endte med readAPI, fordi man her selv kan tjekke HTTP-statuskoden. Det er vigtigt, når NVD begrænser antallet af kald (rate limit).

## Hvad var svært?

Det var også svært at afgøre, hvornår det gav mening at have DTO'erne nested, og hvornår det ikke gjorde. JSON'en fra NVD har mange "grene", og det gjorde det svært at lave DTO'erne.
