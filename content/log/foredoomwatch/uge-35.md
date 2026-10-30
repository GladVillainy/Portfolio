---
title: "Uge 35 - Idéen og scopet"
date: 2026-08-24
project: "foredoomwatch"
---
## Hvad lavede jeg denne uge?

Jeg kom på ideen ForeDoomWatch ud fra to begreber: væsentlighed og værdisættelse.

Væsentligheden kommer af, at jeg selv vil starte et netværk. Her er der brug for et overblik, et dashboard, fordi der er så mange ting at holde styr på. Det kan ForeDoomWatch løse, ved at holde øje med din software og advare dig, hvis den er forældet eller kompromitteret, før det rammer netværket.

Værdisættelsen ligger i selve portfolioprojektet. For mig er det noget, man stolt kan vise frem til en arbejdsgiver, som afspejler hvad man er i stand til at skabe, og hvor produktiv man er. At tage en idé og bygge den op fra bunden, indtil den er i produktion, er ren værdisættelse.

Navnet samler to dele. ForeDoom er at spå dommedagen, altså at blive hacket eller kompromitteret, og Watch er, at applikationen holder øje med dine softwareversioner og om de er forældede eller kompromitterede.

Jeg valgte at starte med privat ejerskab, hvor brugeren ejer sine egne assets, og bygge organisationsejerskab på som en feature senere. Det handler om at starte småt og bygge op, og da det er et eksamensprojekt, er det vigtigere at aflevere et færdigt produkt end et ambitiøst, halvfærdigt et.

Jeg lagde en overordnet dataflow, User til Asset til Finding til Vulnerability, valgte NVD CVE API’et som datakilde og skrev et første udkast til Vulnerability-klassen.